---
{"status":"published","title":"Export Your NPM package list as simple text","dg-permalink":"export-your-npm-package-list-as-simple-text","created":"2025-11-16T15:03","dg-publish":true,"permalink":"/export-your-npm-package-list-as-simple-text/","dgPassFrontmatter":true,"updated":"2025-12-15T23:56:50.878+01:00"}
---

# Backup And Reimport Your NPM Package List As Simple Text

By default, `npm list -g` outputs a terminal-formatted output, i.e.:

```
/Users/thinh/.nvm/versions/node/v24.4.1/lib
├── @google/gemini-cli@0.15.3
├── @musistudio/claude-code-router@1.0.67
├── @openai/codex@0.58.0
├── corepack@0.34.4
├── mcp-chrome-bridge@1.0.29
├── netlify-cli@23.11.0
├── npm@11.6.2
├── repomix@1.9.1
└── safe-rm@3.1.2
```

If you ever want to backup your list of packages import back, you'll need to export it either in JSON using `npm list -g --json`, or as a plain text file with one package name per line, which I prefer. To do this, you can use this neat little command:

```bash
npm list --global --parseable --depth=0 | sed '1d' | awk '{gsub(/\/.*\//,"",$1); print}' > ~/path/to/npmfile-backup
```

To import the packages from the saved list, use:

```bash
xargs npm install --global < ~/path/to/npmfile-backup  
```

