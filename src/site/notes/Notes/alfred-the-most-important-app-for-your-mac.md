---
{"title":"Alfred, The Most Important App For Your Mac","slug":"alfred-the-most-important-app-for-your-mac","created":"2020-11-10T09:00:00.000Z","updated":"2025-04-18T15:53:21.312+02:00","dg-publish":true,"dg-list-home":true,"project":["[[noobthink.com]]"],"tags":["article"],"permalink":"/notes/alfred-the-most-important-app-for-your-mac/","dgPassFrontmatter":true}
---

# Alfred, The Most Important App For Your Mac
Many people I know use a mac. People I work with or friends. Surprisingly though, a lot of them—too many—don't use [Alfred](https://www.alfredapp.com/).

Why is it surprising? Because it's probably **the most important app you will install on your mac**. It is for me. It's the very first app I install on a new mac. It's also one of the main reasons why I can't imagine returning on a Windows machine.

In the first two sections, I'll explain what is Alfred essentially, and why it's a vital piece of my daily workflow. So if you already know Alfred, you can skip those parts. Then, I'll show you exactly how I use Alfred every day, how I customized it, and which workflows (i.e. Alfred's _plugins_) I have installed.

## What is Alfred

At its core, Alfred is an app launcher. It enables you to **launch apps without touching your mouse**. You fire Alfred, type a few letters and boom, you launch the desired app.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20launch%20apps.gif)

You can also search for any file on your computer, if your remember any part of its name.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20search%20files.gif)

Yes, just like Spotlight. But a lot, lot, more powerful. To be fair, [Spotlight got a nice overhaul](https://www.macworld.com/article/2369722/hands-on-with-os-x-yosemite-spotlight-takes-center-stage.html) a few years ago, with the release of Mac OS X Yosemite, and t's a great way to launch your apps and find files.

But as I'm about to show you, Alfred is much, much more than that.

## Why Alfred is paramount to my workflow

I use Alfred every single day, and every single hour that I'm on my computer. What makes Alfred so powerful and invaluable to me are the integrated (as in _default_) features, plus its customizability.

The default features are comprehensive and already useful. But the possibilities of customization with Alfred are almost limitless, either by adding custom configurations to the default features, or by adding [Alfred workflows](https://www.alfredapp.com/workflows/).

First, let me go over a few of Alfred's default features, to show you how practical it is out of the box. Then I'll talk to you about the more advanced use of Alfred, with custom configurations and workflows.

## Alfred's base features

Just with its base features, Alfred is already much more useful than Spotlight.

To access them, once you installed Alfred, all you have to do is hit the selected keyboard shortcut to trigger Alfred, and it will obediently wait for your input. I chose **⌘ + Space** (Command key + Space bar), which actually replaces Spotlight's default shortcut (which I changed to **⇧ + ⌃ + Space**).

### A powerful file search and manipulation

For starters, **searching for a file is a lot more practical in Alfred than in Spotlight**. Not in terms of accuracy, as both are great at finding what you query. The simple, yet huge difference is in the fact that, with Alfred, you're actually dealing with the file themselves. Let me explain.

When you perform a search in Spotlight, it displays a list of results. These results are just a list of items you can highlight or click, but that's it. If you click on a result, it opens. You can't even right click to do additional actions.

On the other hand, with Alfred, **the results are the actual elements themselves**, i.e. they're the files and folders you can directly take action upon. You can drag and drop them directly from the result list. Say for instance, you want to copy a file to a folder you currently have open. But you're not sure where this file is stored. You just remember its name. All you have to do is look it up in Alfred, then drag and drop it.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20file%20manipulation.gif)

Alfred also gives you an easy way to perform various actions on the folders or files you searched. Just by hitting the right arrow on an highlighted result, you get a cool menu offering a handful of practical actions. You can perform an action either by hitting the associated hotkey (**⌘ + 1** to **9**), or filter the list by typing:

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20file%20manipulation%202.png)

### Web Search

What are the top sites that most of us browse daily? Google, Twitter, YouTube, or Amazon. Now, say you want to look something up on one of these websites. What do you do?

Usually, you:

- Open a new tab in your web browser
- Either click on a bookmark, or click the address bar and enter the website's URL
- Click on the website's search field, and start your search.

You probably do it several times a day. Come on, who has got time for that?

Alfred knows that, so the **Web Search** feature lets you perform a search on your most used websites, in a snap. Just launch Alfred—no matter which app or screen you're using—and start typing a Web Search keyword, followed by your search terms.

To find Web Search keywords, simply go to **Alfred's preferences → Features → Web Search**. By default, you can already perform quick searches on most major websites: Google, Google Drive, Google Maps, Gmail, Amazon, Wikipedia, Twitter, Linkedin, Facebook, eBay...

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search.gif)

But the greatest thing about this feature is you can actually create your _own_ custom searches. For most websites, a search is simply a URL containing search terms. For instance, when you search for "best noise canceling headphones" on Google, you're simply browsing to the following URL:

```
https://www.google.com/search?source=hp&q=best+noise+cancelling+headphones
```

I've simplified the URL a little bit, because Google usually adds a bunch of URL parameters for their own tracking needs, but this is the gist.

As you can see, the URL consists of two parts: the website address (`https://www.google.com/search`) and your search query (`?q=best+noise+cancelling+headphones`).

**This means you can create a Web Search for almost any website you use often**, as long as this website allows performing a search via URL. For instance, if you find yourself always looking for WordPress plugins, you will notice that the URL, when you perform a plugin search on WordPress' official website, is like this:

```
https://wordpress.org/plugins/search/woocommerce/
```

Just isolate the base domain part of the URL (`https://wordpress.org/plugins/search/`), and the search terms part of the URL (`woocommerce`). Just replace, in the URL, the part where the search term should be with `{query}`.

Now you can create a Web Search like this:

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20custom%20web%20search.png)

That's not all. You can actually create custom web searches that don't search for anything. Why would you do that? So you can actually launch websites just by typing a keyword. I find it a lot more useful than regular bookmarks. For instance, I regularly use the website UberSuggest. I've configured in Alfred a Web search using the URL of the website, without any query parameter. This way, I just have to type "Ubersuggest" in Alfred, and it launches.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20typed%20bookmarks.png)

I will give you all the custom web searches I created a bit later in this post.

### Web Bookmarks

If you use bookmarks anyway, Alfred has a feature that allows you to search in your bookmarks. Just type a part of a bookmark's URL in Alfred's search bar, and voilà! Another lot of window switching and clicking saved.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20bookmarks.png)

### Calculator

If you need to perform a simple, quick calculation, don't bother launching the Calculator app. That's too long. Just type it directly in Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20calculator.gif)

If you wonder, the calculation I typed was totally random.

### Dictionary and spelling

Not sure about what a word means? Before Alfred, you'd have to go do a google search or start the Dictionary app manually. Now, with Alfred, just type "Define {word}" and you'll get the definition instantly.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20define.png)

Or if you're unsure of how to spell a word, type "Spell {xxx}", where "xxx" would be a word spelled incorrectly. Alfred will suggest you the correct words matching the incorrect spelling.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20spell.png)

### Contacts

Just type a contact's name, and if it's stored in your contact list, Alfred will find them and quickly show you their information. You'll be able to quickly copy their info, like phone or email, too.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20contacts.png)

### System commands and parameters

Alfred lets you type system commands directly, rather than having to go to menus and click things. For instance, if you want to:

- put the computer to sleep,
- restart it,
- empty the trash,
- lock the screen,
- launch the screensaver,

just type it in Alfred. You can even hide, quit and force quit apps, and adjust the computer's volume.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20system%20commands.gif)

You can also quickly access system preferences by their name. For example, if you want to go to the Screen Saver preferences pane, just type "Screen".

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20system%20preferences.png)

## Never open Finder anymore

I gave this feature its own section because it's probably the feature I use most, and which saves me the most time. This alone makes Alfred indispensable.

A big chunk of our time in front of the computer is spent looking for folders and files, and moving them around. With Alfred, opening Finder and browsing folders to find a file is a thing of the past (as long as you remember some part of the file's name).

I can't remember when was the last time when I actually opened Finder to _look for a file_. Whenever I need a file, I just launch Alfred, hit the spacebar (to toggle the file search mode) and start typing the filename. The speed at which Alfred enables you to find files is crazy.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20file%20search.gif)

Once you found your files, you can take actions upon them, right inside Alfred. That's why I almost never use Finder. From Alfred, you can open it, copy or move it to another folder, copy its path, email it, delete it, rename it, etc.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20file%20options.gif)

You can even search _within the content_ of files by starting your search with the keyword `in`.

Once you get used to it, it's a complete game changer. You can do everything and anything in just a few keystrokes.

## Alfred's advanced features (PowerPack required)

For the next functionalities, you'll need to get [Alfred's PowerPack](https://www.alfredapp.com/powerpack/). It's a paid upgrade which unlocks the most powerful features. It's £29, which to me—and anyone who values even a tiny bit their time—is a no-brainer.

### Snippets

Also known as text expansion, it's a cornerstone of productivity. It saves you a ton of repetitive typing. You probably have a bunch of stuff you type all the time. Like your email address, your signature, your physical address, phone number...

There is a [plethora of software dedicated to text expansion](https://thesweetbits.com/best-text-expansion-mac/). Some are great. But once you have Alfred's PowerPack, no need to install another app.

For any text that you happen to type over and over, Alfred's snippets will save you a lot of time.

For instance, instead of having to type

> Let me know if you need anything,

> Thinh

every time, I just type `,let` and Alfred expands it automatically.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20text%20expansion.gif)

I start my auto-expand keywords with `,` because when you normally type, commas are always followed by a space. This way I'm sure I won't auto-expand a snippet by mistake.

Besides, Alfred also lets you insert dynamic content in your snippets. So whenever I have to type the date, I don't have to think. I just type `,date` or `,tod`(for "today"), and Alfred will automatically expand it to the current date in formats I've configured.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20text%20expansion%202.gif)

Here are my most useful snippets:

- `thi@`: automatically expand to my email address [thinh@hey.com](). I have a bunch of these for the different email addresses I own. It's always three letters followed by an **@** sign
- `,thx`: quick signature for emails, expanding to:

> Thanks,

> Thinh

- `,date`: expands to the current date in international format, e.g. 2020-10-20
- `,tod`: same, but in the european format, e.g. 20/10/2020
- `,addr`: expands to my full address (street, city and zipcode)
- `,phone`: expands to my phone number
- `,tob`: expands to my french blog URL, [https://tobal.fr/](https://tobal.fr/). Just like email addresses, I have a few of those, so I can quickly share important URLs easily.

I won't list them all, since the rest is stuff relevant only to me. I have snippets for specific email text related to my projects, or for AirBnB messages I often send. I even have a `lorem` snippet, which automatically expands to a paragraph of [lorem ipsum](https://www.blindtextgenerator.com/lorem-ipsum). That's handy when doing quick web page mockups.

### Clipboard history

I'm amazed by—and fail to comprehend—the sheer amount of people who don't use a clipboard history manager. Do they know how limiting it is to only be able to copy / paste one item? Are they aware of how much time they waste, going back and forth apps and documents to find that bit of text they need?

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20clipboard%20history.jpg?classes=center)

Just like snippets, [there are many awesome clipboard managers](https://www.producthunt.com/ask/646-what-is-the-best-clipboard-manager-for-mac-os), but Alfred's Powerpack has you covered here too. Just hit the selected shortcut (for me it's **⌥ + 1**), and **you can access to all the stuff you copied to the clipboard in the past**, up until a certain time range of your choosing. This can be the last 24 hours, 7 days, 1 month or 3 months.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20clipboard%20history%202.png)

The snippet history popup is simple yet powerful. It both allows you to perform a text search against your clipboard history, while showing you a preview of each clipboard item, then paste it wherever you need it.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20clipboard%20history%203.gif)

Even if you think you're doing fine without a clipboard history manager, just give it a try. I guarantee you'll wonder how you managed to live without it for so long.

Now, let me show you more advanced customizations of Alfred.

## My Alfred custom searches

Obviously, the following customizations fit my own workflow, but you may find that some are useful to you too.

### Domainr

Quickly [get domain ideas](https://domainr.com/). Perfect if you find yourself looking up domains to buy from time to time like me.

Keyword: `domainer`

The search URL is: `https://domainr.com/?q={query}`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20domainr.png)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20domainr.gif)

### Font Awesome

Find an [awesome font icon](https://fontawesome.com/) in seconds.

Keyword: `fa`

The search URL is: `https://fontawesome.com/icons?d=gallery&q={query}&m=free`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20font%20awesome.png)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20font%20awesome.gif)

### IconFinder

Just like Font Awesome, but with more colorful and diverse icons. While Font Awesome is mainly for websites and user interfaces, [IconFinder](https://www.iconfinder.com/) is for big logos in general.

By the way, most of the pretty icons you see in the screenshots (in the settings for a web search in Alfred) come from this website.

Keyword: `icon`

The search URL is: `https://fontawesome.com/icons?d=gallery&q={query}&m=free`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20iconfinder.png)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20iconfinder.gif)

### LibreStock

[LibreStock](https://librestock.com/) is a handy website where you can get cool stock photos for free. So, using Alfred, it's a super fast way to search for an image.

Keyword: `lstock`

The search URL is: `http://librestock.com/photos/{query}`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20librestock.jpg)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20librestock.gif)

### Unsplash

Chances are you've heard at least once of [Unsplash](https://unsplash.com). It's just like LibreStock, but more famous, and I think it has more photos.

Keyword: `unsplash`

The search URL is: `https://unsplash.com/s/photos/{query}?orientation=landscape`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20unsplash.jpg)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20unsplash.gif)

### Ruby on Rails API

I've been playing a bit with [Ruby on Rails](https://rubyonrails.org/) lately. This lets me search quickly in the Ruby on Rails API documentation.

Keyword: `rails`

The search URL is: `https://api.rubyonrails.org/?q={query}`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20rails.jpg)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20rails.gif)

### Symfony documentation

This one lets me search anything inside [Symfony's official documentation](https://symfony.com/doc/current/index.html).

Keyword: `sf`

The search URL is: `http://symfony.com/search?q={query}`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20symfony.jpg)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20symfony.gif)

### UberSuggest keyword research

I recently started using Neil Patel's [Ubersuggest](https://neilpatel.com/ubersuggest/) as my keyword research tool. This enables me to check a keyword's performance in a few keystrokes.

Keyword: `us`

The search URL is: `https://app.neilpatel.com/fr/ubersuggest/overview?keyword={query}&locId=2840&lang=en`

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20ubersuggest.jpg)

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20web%20search%20ubersuggest.gif)

It's quick and easy to add a custom Web Search, and the possibilities are limitless. So don't be shy, go ahead and start creating your own custom searches.

## My Alfred workflows

**Now, we're entering the area where Alfred gets incredibly powerful**. Workflows are to Alfred what extensions are to Chrome. They enable Alfred to perform almost _any task_ you can think of.

Thanks to a powerful visual interface, in which you can create various elements and connect them, combined with support for many scripting language (Apple Script, PHP, Ruby, Python...), you can accomplish pretty much anything that you can achieve with a computer, in just a few keystrokes.

Alfred can take some keywords and data as input, pass them to a script, call APIs, interact with other apps... Your imagination is the limit.

![Ok, it looks scary. But don't worry, Workflows don't have to be that complex.](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20example.jpg)

The Workflow creation interface can be a little intimidating, but you don't have to use it to benefit from Alfred workflows. You can install one of the hundreds of workflows created by the community of Alfred enthusiasts, right from the [official Alfred workflow repository](http://www.packal.org/).

I won't go and list all the existing workflows, since there's about 1485 of them at the time of writing this article. I'll give you the ones I have installed, to give you an idea of what's possible.

### Alfred Browser Toolbox

Adds a bunch of handy keywords and additional menu actions to find and manipulate files right from Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20alfred%20browser%20toolbox.gif)

[Get Alfred Browser Toolbox on Packal](https://www.packal.org/workflow/alfred-browser-toolbox)

### Alfred Maestro

If you use [Keyboard Maestro](https://www.keyboardmaestro.com/main/), this lets you find (with auto-complete suggestions) all your configured Keyboard Maestro macros, and launch them from Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20alfred%20maestro.gif)

[Get Alfred Maestro on GitHub](https://github.com/iansinnott/alfred-maestro). The creator of the workflow warns that it may not work on macOS Catalina, but I 've had no problem so far.

### Audio switch

I often find myself having to switch the audio output of my laptop between my headphones, audio interface or internal speakers. This simple worfklow lets me choose which audio input or output to use without having to touch the mouse.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20audio%20switch.gif)

[Get Audio Switch on Packal](http://www.packal.org/workflow/audio-switch)

### Battery

Another tiny but neat workflow. It shows you useful information about your laptop's battery.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20battery.jpg)

[Get Battery on GitHub](https://github.com/BenziAhamed/alfred-battery)

### Birthday

A silly workflow where you enter your date of birth, then it shows you how many years, months, days, hours, minutes or seconds you lived in total.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20birthday.jpg)

[Get Birthday from Alfred official forum](https://www.alfredforum.com/topic/10733-alfred-time-see-time-passed-from-your-birthday/)

### Convert

This fantastic workflow lets you quickly convert between many units. Currency, distance, duration, mass, speed, memory, volumes... Check out [the whole list of supported units](https://github.com/hgrecco/pint/blob/master/pint/default_en.txt) if you're curious.

I use it daily to convert viscosity coefficients into Magnetomotive force. Just kidding, it lets me convert euros to dollars without having to use Google.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20convert.gif)

[Get Convert on Packal](http://www.packal.org/workflow/convert)

### Alfred Emoji codes

Find yourself using emojis all the time, but hate losing time searching for the right one in your mac's default emoji picker? This workflow will be your savior. It lets you search emojis using text, right from Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20emoji.gif)

[Get Emoji codes on GitHub](https://github.com/carlosgaldino/alfred-emoji-workflow). Although the documentation says it's for Alfred 2, and the workflow hasn't been updated in years, it works perfectly with Alfred 4.

### Host File Manager

If you do some web development, chances are you have to edit your `/etc/hosts` file from time to time. You can open it in a text editor, or in [vim](<https://en.wikipedia.org/wiki/Vim_(text_editor)>) from the terminal, like most people do. Or you can use Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20hosts.jpg)

[Get Host File Manager on Packal](http://www.packal.org/workflow/hosts-file-manager)

### New Google Docs

A simple workflow, but super useful if you often create Google Docs. As the name suggests, it enables you to create a new Google Docs, Sheets, Slides or Form document in a few keystrokes. Just type `new` and select which type of document to create.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20new%20google%20docs.gif)

[Get New Google Docs on GitHub](https://github.com/mathewcropper/alfred/tree/master/new-google-docs)

### New Spark calendar event

I created this one. For my calendar needs, I use Google Calendar. One thing I love using is natural input to create new events. For instance, I would type "Workout every Monday 3PM-5PM" to create a recurring event. Sadly, Google removed this feature a few years ago. As a workaround, I use the [Spark mac app](https://sparkmailapp.com/), which supports natural language input.

So, this workflow lets me quickly create a calendar event, using natural language directly in Alfred. All it does really is launch an [AppleScript](https://www.smashingmagazine.com/2009/05/mac-hacks-17-applescripts-to-make-your-life-easier/) to open up the Spark app, and paste the text into the new event creation popup. It can easily be modified to use any other app that supports natural language.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20new%20calendar%20spark.jpg)

[Download this workflow](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/New%20Spark%20calendar%20event.alfredworkflow)

### Notion Search

[Everybody is waiting](https://medium.com/keep-productive/why-notions-api-will-change-everything-862d86d273b2) for the official Notion API. Meanwhile, a clever developer found a way to interact with Notion anyway, and created this workflow that lets you use Alfred to search for anything in Notion.

It's a bit trickier to configure than other workflows, but it's not hard either. What's great about it is you get autocomplete suggestions. If you heavily use Notion like me, you're going to like it.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20notion%20search.gif)

[Get Notion Search workflow and installation instructions on GitHub](https://github.com/wrjlewis/notion-search-alfred-workflow). It's not difficult to setup, but you want to pay attention to the installation instructions.

### Password Generator

Quickly create safe passwords. I don't use it often nowadays because I use [1Password](https://1password.com/). But if you don't use a password manager, this workflow will be helpful. You can generate various types of passwords, choose their length and complexity.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20password%20generator.gif)

[Get Password Generator on GitHub](https://github.com/deanishe/alfred-pwgen)

### PHP Docs

Big time saver if you do some PHP development. This workflow lets you search quickly in the PHP official documentation. It even offers suggestions as you type.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20php%20docs.gif)

[Get PHP Docs on Packal](http://www.packal.org/workflow/php-docs)

### Pocket for Alfred

If you use Pocket to save your articles, this workflow lets you manage everything you have in Pocket right with Alfred. You can list the content you saved, browse the different categories, open a link, archive or delete items. And, of course, you can search anything by text. I don't remember the last time I opened the Pocket app or website.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20pocket.gif)

[Get Pocket for Alfred on Packal](http://www.packal.org/workflow/pocket-alfred)

### Recent downloads

This small workflow simply shows you a list of your recent downloads by typing `recent`.

[Get Recent Downloads on Packal](https://github.com/ddjfreedom/recent-downloads-alfred-v2)

_Note: while searching for this workflow's download link, I stumbled upon a [more recent and interesting](https://ldstephens.medium.com/recent-items-4-2-for-alfred-3-418829ec07c9) version of this workflow, which allows you to list other recent stuff (recent docs, apps, folders, etc.)_

### Alfred Reminders

Just as with calendar events, I like to be able to create [Apple reminders](https://support.apple.com/en-gb/guide/reminders/welcome/mac) using natural language input. This nifty workflow lets you do that directly from Alfred. It may be not as fast as saying "Siri, remind me to ...," but it's much faster than having to unlock your phone or computer and launch the Reminders app.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20reminders.gif)

[Get Alfred Reminders on GitHub](https://github.com/surrealroad/alfred-reminders)

### Search Notes

Although I use heavily [Notion](https://www.notion.so/) and [Roam Research](https://roamresearch.com/), I often use Apple Notes for quick, on-the-go note-taking. It's snappier and faster for jotting down things, especially from the phone. As you can guess, with this workflow, you can quickly search for anything inside your notes, from Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20search%20notes.gif)

[Get Search Notes on Packal](http://www.packal.org/workflow/search-apple-notes)

### Searchio!

Alfred's base Web Search feature lets you search for anything on any website, including search engines. That's great, but you can only search for the thing you _type_. With Google Search, for instance, you don't get the search suggestions that you would get if you used the website.

The Searchio workflow fixes that. It lets you perform web searches on most major websites, with autocomplete suggestions _within_ Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20searchio.gif)

[Get Searchio! workflow on GitHub](https://github.com/deanishe/alfred-searchio)

### Spotify Mini Player

If you're using Spotify, you're going to love this workflow. It lets you take full control of Spotify right from Alfred. You can search for or play any song in Spotify, browse albums, playlists, show a little popup of the song being played, like or follow songs, artists, albums... Pretty much anything you can do with the Spotify app. The workflow's website lists all that's possible, and it's impressive.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20spotify%20mini%20player.gif)

[Get Spotify Mini Player on the official workflow website](https://alfred-spotify-mini-player.com/)

### Timezones

A simple utility workflow to show what's the time in different timezones.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20timezones.gif)

[Get Timezones on Packal](https://www.packal.org/workflow/timezones)

### Unicode Symbol Search

You don't know how this workflow is useful until you need to type specific characters like , ©, or ⌘.

Instead of having to look up on Google then copy paste, or memorize crazy key codes, this workflow lets you find any [unicode character](https://www.smashingmagazine.com/2012/06/all-about-unicode-utf8-character-sets/) by name, inside Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20workflow%20unicode%20symbol%20search.gif)

[Get Unicode Symbol Search on Packal](https://www.packal.org/workflow/symbols-search)

## One last quick tip

Since Alfred 4, you can quickly access any settings, options or customization available in Alfred, by typing "**?** " followed by the settings label. \#Alfredception.

Say you want to quickly access the configuration screen for snippets, just type **?snippets** in Alfred.

![](https://tobalfr.s3.eu-west-3.amazonaws.com/uploads/2020/10/Alfred%20-%20settings%20quick%20access.gif)

## Conclusion

I can't overstate how vital Alfred is to my workflow. I haven't counted the hours it saved me, but if I had to guess, I'd say it is in the ballpark of _weeks_.

It's so important that it's the very first app I install on any new mac. I simply cannot imagine using my mac without it. Just give it a try—a real try, for a few weeks—and you'll know what I mean.
