---
{"status":"published","project":"[[NoobThink]]","dg-publish":true,"created":"2023-06-30T10:55:00","permalink":"/notes/fixing-shitty-image-when-connecting-tv-to-computer/","dgPassFrontmatter":true,"updated":"2025-12-16T00:08:19.680+01:00"}
---

# Fixing Shitty Image When Connecting TV To Computer

I connected my LG 43" TV to my MacBook Air, got shitty image:
- super laggy, mouse cursor would move by 100-200ms delay, unusable
- desktop cropped (couldn't see menu bar)
- washed out colors

## How I fixed it

Here's how I fixed it:
- Fixing input lag (also called display lag)
	- First thing is to make sure the refresh rate setting is correct ( ≥ 60hz) in Displays > 
		- If refresh rate option is 30hz max, make sure the proper resolution is selected
			- I had selected a weird resolution (2040x1080), that's why higher refresh rates were not available
		- I chooses 120Hz, it's best
		- If you can't still pick a higher refresh rate, make sure:
			- your TV actually supports 60Hz+ refresh rate and 
			- you use a proper HDMI cable, at least 2.0 (1.4 and lower are locked at 30Hz on resolutions higher than 1080p)
	- Set your TV to Gaming mode.
		- Specific settings for LG TV:
			- Picture mode: Game
			- Go toy All settings > Picture > Additional Settings
				- Make sure HDMI Ultra HD deep Colour is eneabled for your HDMI port
				- Make sure Instant Game REsponse is enabled for your HDMI port			
- Fixing cropped image
	- Go toy All settings > Picture > Additional Settings
		- Go to aspect ratio -> Original
		- Just Scan -> turn it On. This fixes common problem known as [Overscan](https://support.apple.com/en-us/HT202763). By default it's on *Auto* and usually this means it's off.
	- This should solve the cropped image problem.
- Fixing washed out colors
	- Simply go to your computer settings and test different color profiles.
	- For my MacBook Air, it's in Display > Color Profile.

Sources:
https://www.reddit.com/r/AMDHelp/comments/so91m3/got_a_48_lg_c1_and_i_cant_get_the_screen_to_fit/
https://tongfamily.com/2020/12/15/finaly-fixed-overscan-on-a-lg-c9-or-cx/
