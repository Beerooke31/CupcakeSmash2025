+++
title = "8. SMASH IT"
weight = 8
chapter = true
pre = ""
+++

# Smashing the cupcakes

Now that our cupcakes are merrily popping up and down, let's write a function to 'smash' them! The end goal of our game is to see how many of our cupcakes we can smash in the allocated time.

To do this, we're going to create another function called `smash` to run whenever a cupcake is clicked. When this happens, we also want to remove the `up` class from the hole the cupcake is in so that the smashed cupcake pops down again. 

Up until now, we haven't actually referenced our cupcakes, only the holes. In our HTML (the skeleton of our game) that was provided, our cupcakes are children of our holes:

```html
<div class="hole"> <!--- this is our hole opening tag --->
    
      <button onclick="smash(this)" class="cupcake"></button> <!--- this is our cupcake --->
    
</div> <!--- this is our hole closing tag --->
```
Because we want to run a function on the hole (to remove the `up` class) but the click is on the cupcake, we need to use the[`parentNode`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode) property to get our cupcake to pop back down when clicked. Add the new code below to create your `smash` function. It will write a message to the console (remember you can show and hide this from the bottom left in CodePen) and cause the cupcake to disappear when clicked.

```js
function smash(cupcake) {
	console.log('smashed!')

	cupcake.parentNode.classList.remove('up')
}
```

You can read more about nodes and parent nodes here:   
[parentNode](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)
