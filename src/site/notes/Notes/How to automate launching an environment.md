---
{"status":"published","project":"[[NoobThink]]","created":"2022-07-29T20:18:00","dg-publish":true,"permalink":"/notes/how-to-automate-launching-an-environment/","dgPassFrontmatter":true,"updated":"2025-12-15T23:45:30.358+01:00"}
---

# How to automate launching an environment on MacOS
When I start my day job I always launch the same apps. Doesn't take long, but still, every single day repeating the same things for 2 minutes adds up.
Now that macOS has the Shortcuts app, you can make it super quick to start all the apps you need in seconds.

Start the Shorcuts app, and create a new shortcut.
You only need 1 action, the *Run Applescript* command (leave *with input* empty).
Inside this action, you can put whatever applescript you want. 
Here's mine for example:

```applescript
tell application "iTerm" to activate
tell application "System Events"
	delay 1
	keystroke "ssh dockerdev"
	keystroke return
	keystroke return using {control down, option down}
	delay 1
	keystroke "cd cloudifi/cloudi-fi"
	keystroke return
end tell

tell application "PhpStorm" to activate
delay 2
tell application "Fork" to activate
delay 2
do shell script "open -na 'Brave Browser' --args --profile-directory='Profile 2'"
```

It's my development enviroment launch routine.
- It starts iTerm and connects to a server using SSH.
- It starts PhpStorm.
- It starts Fork.
- It starts Brave Brower with a specific profile dedicated to my day job.

If the Shorcuts app complains that it can't handle keystroke, you need to authorize the app in the accessibility section of the Security & Privacy system preferences, along with the *siriactionsd* app. [^1]

---
## References
[^1]: https://developer.apple.com/forums/thread/696461

https://apple.stackexchange.com/questions/389529/use-apple-script-to-open-chrome-with-specific-profile
https://mybyways.com/blog/sending-keystrokes-to-an-application-using-shortcuts-for-macos-monterey
