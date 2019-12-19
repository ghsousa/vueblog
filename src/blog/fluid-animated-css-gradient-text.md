---
title: Fluid Animated CSS Gradient Text Effect
date: 2019-02-12 20:47:18
excerpt: A walk through on how to create a simple animated gradient using CSS Animations
description: Gabe Sousa | A walk through on how to create a simple animated gradient using CSS Animations
type: post
blog: true
tags:
  - CSS
  - WebDev
---

CSS animations are awesome. Not only do they make great <a href="https://codepen.io/astrixsz/pen/RRxyKz">digital art pieces</a>, they also give us the ability to add fluid design elements, right into our web pages. 

Recently, I integrated a CSS gradient animation in many of my blog links to give them a living, liquid feel to them. See my 'Recent Essays' module below

![](https://thepracticaldev.s3.amazonaws.com/i/dgbkiccdcmzkaaqjp78l.gif)

_note: gif is sped up for demonstration purposes_

Neat, right? And fairly simple to accomplish. All we really need is CSS!

```css
a {
  animation: flow 30s ease-in-out infinite;
  background: linear-gradient(-60deg, #904e95, #e73c7e, #ee7752);
  background-size: 300%;

  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

### Let's deconstruct it

So first thing in my CSS is the animation rules.

```css
a {
  animation: flow 30s ease-in-out infinite;
}
```

Here, I'm saying - play the animation named **flow** for a duration of **30 seconds**. Set the animation to **ease in and out** for a smoother effect, and have the animation loop for an **infinite** number of times.

Then there are the background rules.

```css
a {
  background: linear-gradient(-60deg, #904e95, #e73c7e, #ee7752);
  background-size: 300%;
}
```

I set my background to be a **linear-gradient** and give it my desired colors. _For beautiful gradients I use often <a href="https://uigradients.com/">UI Gradients</a> when I can't come up with anything nice._ I then stretch out the background to 300% the size using the **background-size** property to give the animation room to move.

I then set the **background-clip** to be **text** and set the **text-fill-color** to be **transparent** so my default font color doesn't interfere with my gradient.

```css
a {
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

Now on to the actual animating. I create a keyframe animation named flow and set up keyframes at the zero, fifty, and one-hundred percent marks.

```css
@keyframes flow {
  0% {
    background-position: 0 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0 50%;
  }
}
```

Final result:
![](https://thepracticaldev.s3.amazonaws.com/i/ms7hu4num9zl7w9atgkz.gif)

And there you have it - a nice, fluid animated gradient over text. Just another little fun design element courtesy of CSS.
