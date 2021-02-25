+++
title = "Step 6"
weight = 6
chapter = true
pre = ""
+++

# Smashing the cupcakes

Now that the cupcake is popping up and down, we also need to make sure we can smash the cupcakes, so we'll create another function called `smash` to run whenever a cupcake is smashed. When this happens, we also want to remove the `up` class so the cupcake pops down again. Because we're getting the cupcake this time, we also need to fetch it's parent (`parentNode`), which is the hole.

```js
function smash(cupcake) {
	console.log('smashed!')

	cupcake.parentNode.classList.remove('up')
}
```