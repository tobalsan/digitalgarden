---
{"status":"published","project":"[[NoobThink]]","dg-publish":true,"created":"2023-05-03T23:39:00","permalink":"/notes/replicate-roam-research-tomorrow-command-in-obsidian/","dgPassFrontmatter":true,"updated":"2025-12-16T00:00:33.589+01:00"}
---

# How to replicate Roam Research `/tomorrow` command in Obsidian

Use [Templater](https://silentvoid13.github.io/Templater/internal-functions/internal-modules/file-module.html#tpfilefind_tfilefilename-string).

Writing a [script template](https://www.thoughtasylum.com/2022/03/29/auto-link-and-generate-page-in-obsidian/).

In case you want to open the file after creating it ([source](https://gist.github.com/thomasvs/343c740825407f0a84f350e4e40bedd0)):

```js
const file = app.vault.getAbstractFileByPath(filePath)
app.workspace.activeLeaf.openFile(file); 
```

Go into Obsidian > Community plugins > Templater settings, create a template hotkey entry for a templater template:
![CleanShot 2023-06-20 at 18.20.57.png](/img/user/Files/CleanShot%202023-06-20%20at%2018.20.57.png)

You don't have to specify a hotkey in the **Hotkeys** settings, just adding it from Templater settings will make it available as slash command.
