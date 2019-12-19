---
title: Slots, Props, and Vue
date: 2019-10-27 10:43:18
excerpt: 
description: Gabe Sousa | Exploring single file components in the Vue framework
type: post
blog: true
tags:
    - Vue
    - WebDev
---

OUTLINE
* Intro (How Vue works)
* Props 
	* What are Props
	* How Props work
* Slots
	* Whare are Slots
	*	Ho*w Slots Work
* Comparison
	* Which do I use

In Vue.js,  we hierarchically build our applications through the use of components. We create component trees, which have data moving from parent components down to their children through `props`. Similarly, we can move data from child components up to their parents via slots or `v-slot`.

### Props
Props are custom attributes you can delegate to a component.  They are the way that we transfer data from a parent component down to its child components.

```vue
<template>
  <greeting>{{name}}</greeting>
</template>
<script>
  props: ['subject', 'question', 'answer', 'cardNumber'],
</script>
```

In the example above our props are listed in an array, however, we could also have our props listed out as an object like so:

```js
  props: {
  subject: String,
  question: String,
  Answer: String,
  cardNumber: Number  
}
```
Writing our props as an object allows us to give each property a specific type of value and validate our data.



* Props are read-only
* Props are passed down the component tree to its child elements.
* Props can not pass data up the tree, this is done to stop child components from modifying the parent's state.

### Slots
Slots allow us to write our components a little differently in Vue.  