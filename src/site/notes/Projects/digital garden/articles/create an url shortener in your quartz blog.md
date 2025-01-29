---
{"title":"Create An URL Shortener in your Quartz Blog","dg-permalink":"url-shortener-in-quartz-blog","created":"2025-01-22T14:45","project":["[[noobthink.com]]"],"dg-publish":true,"dg-path":"create an url shortener in your quartz blog.md","permalink":"/url-shortener-in-quartz-blog/","dgPassFrontmatter":true,"updated":"2025-01-22T15:05:45.266+01:00"}
---

# Create An URL Shortener in your Quartz Blog
Here's how to create a simple URL shortener for your Quartz blog. This guide will walk you through implementing a redirect feature using a custom Quartz plugin. This allows you to specify a `redirectUrl` in your markdown frontmatter, turning your blog page into a redirect to another site. It's pretty barebones (no click tracking, no UI to manage the redirects) but it does the job.

## Crafting a Redirect Emitter Plugin

First, you need to create the core plugin responsible for generating the redirect pages. Create a new file at `quartz/plugins/emitters/RedirectEmitter.ts` with the following content:

```typescript
import { QuartzEmitterPlugin, BuildCtx, ProcessedContent, StaticResources } from "../types";
import { FilePath } from "../../util/path";
import { promises as fs } from "fs";
import path from "path";

interface Options {
  enableRedirects?: boolean
}

const defaultOptions: Options = {
  enableRedirects: true
}

export const RedirectEmitter: QuartzEmitterPlugin<Options> = (opts?: Options) => ({
  name: "RedirectEmitter",

  getQuartzComponents(ctx: BuildCtx) {
    return [];
  },

  async emit(ctx: BuildCtx, content: ProcessedContent[], resources: StaticResources): Promise<FilePath[]> {
    const filePaths: FilePath[] = [];

    for (const [tree, file] of content) {
      const redirectUrl = file.data?.frontmatter?.redirectUrl;

      if (redirectUrl) {
        const targetUrl = redirectUrl.startsWith('http') ? redirectUrl : `/${redirectUrl.replace(/^\//, '')}`;

        const redirectHtml = `
<!DOCTYPE html>
<html lang="en-US">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="refresh" content="0;url=${targetUrl}">
    <script>
      window.location.replace("${targetUrl}");
    </script>
    <title>Redirecting...</title>
</head>
<body>
    <p>Redirecting to <a href="${targetUrl}">${targetUrl}</a>...</p>
</body>
</html>`;

        const outputPath = path.join(ctx.argv.output, file.data.slug! + ".html");
        await fs.mkdir(path.dirname(outputPath), { recursive: true });
        await fs.writeFile(outputPath, redirectHtml);
        const fp = file.data.slug! + ".html";

        filePaths.push(fp);
      }
    }

    return filePaths;
  },
});
```

This code defines a `RedirectEmitter` plugin. Let's break down what's happening:

- **Imports**: It imports necessary types from Quartz and modules for file system operations and path manipulation.
- **Options Interface**:  It defines an `Options` interface to optionally configure the plugin. Currently, it only includes `enableRedirects`, set to `true` by default.
- **Plugin Definition**: `RedirectEmitter` is defined as a `QuartzEmitterPlugin`. Emitter plugins in Quartz are responsible for taking processed content and outputting files.
- **`emit` Function**: This is the core of the plugin. It iterates through each file in your content.
    - It checks for the `redirectUrl` property in the frontmatter of each file.
    - If `redirectUrl` exists, it constructs the `targetUrl`, ensuring it's properly formatted (adding a leading `/` if necessary for internal redirects, or keeping it as is for external URLs).
    - It generates minimal HTML for redirection. This HTML uses both `<meta http-equiv="refresh">` and JavaScript's `window.location.replace()` to ensure immediate redirection. This dual approach enhances reliability across different browsers.
    - It writes this HTML to a file in your output directory, using the original file's slug to create the HTML file name (e.g., `my-post.html`).
    - The plugin then adds the generated file path to the `filePaths` array, which is returned to Quartz.

## Registering the Plugin

To enable the `RedirectEmitter`, you need to register it in your `quartz.config.ts` file. Open `quartz.config.ts` and modify the `plugins` array within the `configuration` block to include `Plugin.RedirectEmitter({ enableRedirects: true })`:

```ts
   Plugin.Assets(),
   Plugin.Static(),
   Plugin.NotFoundPage(),
   // The three above should already be present
   Plugin.RedirectEmitter({ enableRedirects: true }),
```

By adding `Plugin.RedirectEmitter({ enableRedirects: true })`, you're telling Quartz to use your new plugin during the build process. The `enableRedirects: true` option is currently the only configuration, and it's set to true by default in the plugin, but it's good practice to include it explicitly.

## Excluding Redirect Pages from Recent Notes

If you leave it at that, it will work but then your redirect pages will appear in your recent notes list. Usually you don't want that. To exclude them, modify the `RecentNotes.tsx` component to filter out pages with the `redirectUrl` frontmatter property.  Open `quartz/components/RecentNotes.tsx` and update the `pages` filtering logic:

```ts
    // Replace this line
    const pages = allFiles.filter(opts.filter).sort(opts.sort)
    // With the following
    const pages = allFiles
      .filter(opts.filter)
      .filter(page => !page.frontmatter?.redirectUrl) // Filter out pages with redirectUrl
      .sort(opts.sort)
    // rest of existing code
    const remaining = Math.max(0, pages.length - opts.limit)
    return (
       <div class={classNames(displayClass, "recent-notes")}>
```

This change adds `.filter(page => !page.frontmatter?.redirectUrl)` to the page filtering chain. This ensures that any page with a `redirectUrl` in its frontmatter will be excluded from the list of recent notes.

## Exporting the Plugin

Finally, ensure your new plugin is exported so Quartz can find it. Open `quartz/plugins/index.ts` and add the following line to the exports:

```ts
// After this line
export * from "./emitters"
// Add
export { RedirectEmitter } from "./emitters/RedirectEmitter"
```

## Using the Redirect Feature

Now, to use the redirect feature, simply add the `redirectUrl` property to the frontmatter of your markdown file. For example:

```markdown
---
title: My Redirect Page
redirectUrl: https://example.com
---

This content will be ignored. You will be redirected.
```

When Quartz builds your site, it will generate an HTML file for this markdown page that immediately redirects to `https://example.com`. The original markdown content will be effectively bypassed, and the page will function as a URL shortener.

Refer to the [Quartz official docs](https://quartz.jzhao.xyz/advanced/making-plugins) if you want to understand plugins in detail.