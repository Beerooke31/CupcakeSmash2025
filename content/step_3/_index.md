+++
title = "Step 3"
weight = 1
chapter = true
pre = ""
+++

# Popping Up Cupcakes

Next we want to create a function to pop our cupcakes up out of the holes. There's CSS styling already set up for most of this so the cupcakes will appear with some pizazz, so we just need to add a class to one of our holes to make the cupcake appear. This will take the first hole from our list we saved earlier, and add the class of `up` to it (which will then do some CSS magic).

```js
function popUp() {
	let hole = holes[0]

	hole.classList.add('up')
}
```

Now we trigger our `popUp` function to run when the game starts, instead of adding a comment in the console log at the start of the game. 

```diff
function startGame() {
-	console.log('Game has started')
+ popUp()	

	setTimeout(endGame, 10000)
}
```

Now try clicking the **Start** button and see what happens!
