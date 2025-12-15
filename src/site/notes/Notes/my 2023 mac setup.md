---
{"project":"[[NoobThink]]","status":"published","dg-publish":true,"created":"2022-07-30T17:26:00","permalink":"/notes/my-2023-mac-setup/","dgPassFrontmatter":true,"updated":"2025-12-15T23:49:35.980+01:00"}
---

# My 2023 mac setup

## First things when installing a new mac
- *Optional*: start the Apple migration from the previous mac. I prefer starting fresh to avoid bringing clutter or unused stuff back.
- Get rid of everything from the dock except the Finder, and the Trash
- Connect my Logitech MX Anywhere 3 via Bluetooth and install Logi Options software to get the useful control gestures. Settings are synced in the cloud so everything is set up exactly as I want automatically.
- Fundamental apps
	- Raycast
	- 1Password 
	- Arc
	- Obsidian
- Useful apps/utilities
	- Rectangle
	- Cleanshot X – best screenshot app so far
	- Spotify
	- Google Drive

## Custom settings
Set the dock to automatically hide, then launch Terminal and type ([source](https://macos-defaults.com/fr/dock/autohide-time-modifier.html#prerequis)):
```
# Disable the small delay before the dock appears
defaults write com.apple.dock "autohide-delay" -float "0" && killall Dock

# Disable the animation when the dock appears so it's super fast
# Note: I don't use 0 because it would look choppy. 0.25 is the sweet spot as it's fast but keeps a bit of effect
defaults write com.apple.dock "autohide-time-modifier" -float "0.25" && killall Dock 
```

Set Arc as the default browser > System Settings > Desktop and Dock, scroll a bit to set the Default web browser

## Code tools
- git (`xcode-select --install` from any terminal)
- brew
- warp – next-gen terminal replacement
- VSCode