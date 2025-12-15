---
{"title":"Customizing Obsidian's Digital Garden Theme","dg-permalink":"customizing-obsidians-digital-garden-theme","project":"[[NoobThink]]","created":"2025-07-07T20:15","tags":["article"],"dg-publish":true,"permalink":"/customizing-obsidians-digital-garden-theme/","dgPassFrontmatter":true,"updated":"2025-07-08T00:16:10.044+02:00"}
---

# Customizing Obsidian's Digital Garden Theme

I haven't tinkered a lot with my digital garden in Obsidian. I thought it was cumbersome to have to go through the plugin settings to change the theme. Turns out you can update it and customizing much more efficiently by just downloading the repo and making changes with a code editor. 

In reality, the Digital Garden plugin simply spins up an [Eleventy](https://www.11ty.dev/) website and adds your Obsidian notes selected for publication. The gazillion themes listed under the plugin settings are really just all the available [Obsidian themes](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Themes/%F0%9F%97%82%EF%B8%8F+Themes). 

So to update and customize your Digital Garden theme:
- Clone the repo locally.
- Edit `./.env` (`THEME` and `BASE_THEME` parameters)
    - For `THEME`, you want to put the full URL to a theme's raw CSS file, e.g. for the [Carbon theme](https://github.com/vhbelvadi/obsidian-carbon), you set it to: `https://raw.githubusercontent.com/vhbelvadi/obsidian-carbon/refs/heads/main/theme.css`. 
- If you want custom CSS, create the `./src/site/styles/user` folder and put it any CSS/SCSS file with your custom rules.
- `npm install` then `npm run start`

It's a bit annoying because even though it looks like the local dev app is doing a hot reload, you actually have to stop the process and run `npm run start` again to see the changes take effect when you modify the `.env` file, or when you add new CSS/SCSS files.  

After all this, you simply need to push your changes to the repository and Netlify should pick up the changes automatically.

Sources:
- [Digital Garden: Adding custom components](https://dg-docs.ole.dev/advanced/adding-custom-components/#notes)

