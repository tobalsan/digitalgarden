---
{"status":"published","project":"[[NoobThink]]","dg-publish":true,"created":"2022-09-09T22:21:00","permalink":"/notes/get-cursor-to-stops-in-camel-case-words-with-vs-code/","dgPassFrontmatter":true,"updated":"2025-12-15T23:51:43.846+01:00"}
---

# How to get cursor to stops at parts of camelCase words in Visual Studio Code

Lately I've been using VSCode a bit more, while PHPStorm remains my main code editor since years now. 
While I was in VSC, something that frustrated me was that, when hitting ALT+left or right arrow, the cursor would skip entire words. PHPStorm has this neat feature where the cursor actually stops *inside* camelCase words, called **CamelHumps**. e.g. if you have a method called `methodThatDoesSomething` , you have to actually hit ALT + arrow 4 times to go from one side to another as the cursor will stop at the end of `method`, then thend of `That,` then the end of `Does`, and finally the end of `Something`. 

it's really a neat feature because more often than not, I find myself wanting to change just some parts of method names or variables, not the entire word. 

Well actually VSCode supports this natively (thankfully no need to install another slowing extension). You just have to hit cmd+K cmd+S to launch the keyboard bindings config, and enter either `cursorWordPartLeft`, `cursorWordPartLeftSelect`, `cursorWordPartRight`, or `cursorWordPartRightSelect` in the search field to customize the key bindings you want to use. I just used the same as PHPStorm, so ALT + left for cursorWordPartLeft, etc.

---
## Reference
https://www.damirscorner.com/blog/posts/20190726-CamelHumpsNavigationInVsCode.html
