---
{"status":"published","project":"[[NoobThink]]","dg-publish":true,"permalink":"/notes/how-to-launch-a-brave-profile-from-command-line/","dgPassFrontmatter":true,"updated":"2025-12-15T23:43:54.628+01:00"}
---

# How to launch a Brave profile from command line
For an automation script on my mac using AppleScript, I wanted to launch a new Brave Browser window with a specific profile.

To do that, you need to know the folder in which the profile is stored.
To know the folder name, open the browser with the desired profile, and go to `brave://version` in the URL bar.
You will find on this page the **Profile Path** info. Use this name, quoted, when launching from terminal:
```bash
$ open -na "Brave Browser" --args --profile-directory="Profile 1"
```

---
## References
https://apple.stackexchange.com/questions/389529/use-apple-script-to-open-chrome-with-specific-profile
https://community.brave.com/t/how-to-force-brave-to-always-open-in-a-specified-profile/275330
