---
title: Four Firefox Dev-Tools I use daily
date: 2019-06-10T02:39:48.644Z
excerpt: Breif overview of Firefox's Highlight, Fonts, Changes, and Scratchpad dev-tools.
description: Gabe Sousa | Breif overview of Firefox's Highlight, Fonts, Changes, and Scratchpad dev-tools.
type: post
blog: true
---
I love Firefox, this is no secret. I find it to be a snappy browser with some phenomenal developer tools built right in.

Most around me use Chrome, (or more recently <a href="https://brave.com/">Brave</a>) and swear by their dev tools. And I'll admit that they're pretty great, I even ended up switching over to Brave for a few weeks and found it to be a fantastic browser. 

However, after weeks of straight usage both at home and at work, I found myself switching back to Firefox. It felt like coming back home when I launched the developer tools, and started working. Functionality-wise, both FF and Chrome are almost identical, *almost*. I'll briefly highlight some of what I think, are the most useful features of Firefox's dev-tools.

#### Highlighting
![](https://thepracticaldev.s3.amazonaws.com/i/d7l7lzltwij632c7u9rx.gif)
One of the most useful features of Firefox's insepctor tool for me is the ability to highlight elements on a page matching any selector I choose. In my example GIF above, I highlight every anchor tag on my homepage which contains the class `.wp-block-latest-posts`. 

This feature is extremely useful when I'm trying to figure out which item or items fall under a certain class name, or need the overview of a certain `div` box-model while I inspect an element directly above it or below it etc. 

Elements will stay highlighted even if you switch over to a different tab in your dev tools. So you can leave an element highlighted while you change over to the fonts tab, or browser console. It's a small feature with many uses.

#### Fonts
![](https://thepracticaldev.s3.amazonaws.com/i/z6y50ennjcpgzi24wg9g.gif)
The fonts tab is a newer addition to the Firefox dev tools. Here, you can get a nice overview of the fonts being used on the current page as well as controls to quickly customize their appearance - from `font-weight`, to `font-size` and even the `line-height`.

#### Changes
I am constantly using the inspector tool to highlight items and make CSS changes right then and there. If I like what I see, I backtrack through my changes and write out the code in my text-editor. 

The changes tab conveniently takes all the CSS revisions that I have made in the inspector tool during my often long sessions and lumps them together so that I can quickly get an overview as to what exactly I did, Firefox even gives me the ability copy and paste directly from here. 

Gone are the days of painfully backtracking through an endless number of elements because I no longer remember what exactly I did to make something look as intended.
![](https://thepracticaldev.s3.amazonaws.com/i/0q59wdiqevqs10jboddm.png)

#### Scratchpad
![](https://thepracticaldev.s3.amazonaws.com/i/5em4872zfnp5ep54g2tv.gif)
Scratchpad is cool, it allows you to write out some JavaScript and execute it when ready. It also allows you to inspect JS objects. 

What I like about Scratchpad is that it works more like a text-editor than a browser console. I can write out my JS as if I were in VS Code and it won't execute until I tell it to run, as opposed to the console which at times I have ran mid way through writing some JavaScript thanks to a slippery finger on the return key.


There are so many other cool Firefox dev tool features I did not get to in this post, such as <a href="https://twitter.com/nicolaschevobbe/status/1135798960361263104">real time CSS tips</a>, or the <a href="https://twitter.com/jensimmons/status/1126570959715098624">CSS Grid Inspector</a>. For further reading into what Firefox's dev tools can do, you can hop on over to their <a href="https://developer.mozilla.org/en-US/docs/Tools">DOCS</a>, I'd also recommend giving their <a href="https://twitter.com/FirefoxDevTools">twitter</a> a follow for the latest on their developer tools. 

Enjoy friends!


