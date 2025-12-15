---
{"status":"published","created":"2022-07-30T16:59:00","dg-publish":true,"permalink":"/notes/fork-is-a-great-git-gui-client/","dgPassFrontmatter":true,"updated":"2025-12-15T23:47:40.200+01:00"}
---

# Fork is a great Git GUI client
When I first learned about git, I heard that CLI was for real developers, and GUI tools for newbies. So for  many years I stuck to using git with the command line interface.

But then I started using PhpStorm about 5 years ago, and since it comes with a neat Git client that does a very good job, I though a GUI client was not so bad. I tried it for about a year and while it's sufficient to get the job done, the interface is a little too austere..

Over the next couple years, I tried  other clients: 
- **SourceTree**. A solid Git client, but I didn't like the commits list layout, nor the tree view. The  interface is a bit too clunky for my taste..
- **Sublime Merge**. I liked it a lot because it sports the same benefits as Sublime Text, namely a super responsive interface, a useful command palette, and an overall nice look. But again I didn't like the tree view. 
As you can guess, the tree view is important to me becaues I work with other people and it's important for me to figure out what is going on inside the repo.

At some point I considered using other clients but ended up passing, like SmartGit. It looks like a powerful client, but the UI is too "linuxy" for me. It would feel like using Gimp. Or Tower, but I always felt like it was more geared toward less techy people. The price tag is also steep with a minimum of $60/year.

This leads us to Fork.

## A powerful and elegant Git client

After spending 18 months with Sublime Merge and scratching my brains on the tree view, I went in search for a Git client that was as powerful but with a more polished interface. That's when I discovered Fork.

The first thing that hit me when I started Fork was the elegant UI. It really looks like a Mac-first app (even though it's available on Windows), and as such it sports a sleek interface with everything you need being easy to find, and nothing feeling clunky. 
But what sealed the deal for me was the tree view. It's just clean, and makes it easy to understand what happened or is happening between the different branches, merge operations, origins, and tags.

The staging and commit experience is great; there's a clever layout for the new, modified, and staged files. The commit box actually makes you want to create great commit messages.
Interactive rebases are a breeze with an interface well thought-out, to let you pick, squash, or reword commits without any confusion.

It also has many small but useful features:
- when it detectes if a repository origin is on Github, GitLab, or BitBucket, and if so offer a context menu to directly go to the repository web page.
- For any action that the client perform, you can see what actually went under the hood with a single click, that shows you what CLI commands were run. 
- Stashing and applying changes is a matter of a couple clicks. 
- Managing branches and tags is a breeze, with everything accessible from the context menu. A simple but killer feature for my usage: the ability to fast-forward multiple branches at a time.

Last but not least, Fork as a command palette to access any repository or command in just a few keystrokes, so you don't even need to use the mouse.

I think it's a fantastic product, which is even more impressive considering it's made by a team of just two. The only thing that could be considered a "downside" for some people is that it's not free like some other Git clients. It's a one-time $49 fee. I paid that fee gladly since it's been my favorite and main Git client since several months.

So if you're in search of a great Git client, give it a try.

[Git Fork website](https://git-fork.com/)