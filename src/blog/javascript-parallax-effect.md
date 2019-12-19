---
title: JS Parallax Effect
date: 2019-02-09 20:47:18
excerpt: Short post going over how we managed to create an easy JS parallax effect using JQuery
type: post
blog: true
tags:
  - JavaScript
  - WebDev
---

I was recently tasked with creating a micro-site for one of our clients at work. This particular client wanted a small site that would showcase their new line of chips and dip. This being my first client deliverable at AMP, I was pretty excited to get started and show my team that I'm more than just a pretty face.

So I meet with my project manager and we go over the designs and discuss the functionality that the page would have behind it's different sections. It was pretty straight forward, a hero, a featured products grid, a store locator, a product carousel and a footer. Only thing is the hero would feature a parallax effect where some chips would pop out and move up the page as the user scrolls down. While this was going to take a bit of work, a major bonus for me was that most of the other pieces of the site were already built for me thanks to my co-worker Ethan who is a pro at cranking out these micro sites for our clients. So I pull down his github repository and setup my local, we're using Zurb's foundation framework for this client. I start putting together the pieces and building out the page according to the designer's comp. After about 3 - 4 hours I finish what I consider the base of the page. I have all the sections in place and all the components are functioning as expected. It was time to get to the parallax effect.

## 9 lines of JavaScript

No bullshit. After hours of playing around with different parallax libraries to try and create the effect I wanted, my boss casually slides over in his chair and says "That looks fun. Send this to me, let me give it a shot". So I do. 15 minutes later he sends me over a JavaScript file and tells me that its all set. I copy his code into my JavaScript file, compile it and open it up in FireFox to test it. It worked. It worked beautifully. I was so amazed, I kept scrolling back and forth making the chips move for what felt like hours. See the code below.

```javascript
var $chips = $(".chip");
$chips.each(function(i, el) {
  var randInc = 1 + Math.random() * 3;
  $(window).scroll(function() {
    var distance = $(window).scrollTop();
    var chipMargin = -1 * (distance / randInc);
    $(el).css("margin - top", chipMargin);
  });
});
```

Pretty Cool. And wicked simple too. Granted with this version you need jQuery in order for it to run, but creating the same result in vanilla js is possible.
