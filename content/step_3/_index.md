+++
title = "Step 3"
weight = 1
chapter = true
pre = ""
+++

# Popping Up Cupcakes

Next we want to create a function to pop up the cupcakes. There's CSS already set up for most of this, so we just need to add a class to the hole to make the cupcake appear. This will take the first hole from our list we saved earlier, and add the class of `up` to it (which will then do CSS magic).

```js
function popUp() {
	let hole = holes[0]

	hole.classList.add('up')
}
```

Now we trigger our `popUp` function to run when the game starts, replacing the console log at the start of the game. Now try clicking the **Start** button and see what happens.

```diff
function startGame() {
-	console.log('Game has started')
+ popUp()	

	setTimeout(endGame, 10000)
}
```