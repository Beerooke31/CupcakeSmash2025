+++
title = "3. Cupcake Time"
weight = 3
chapter = true
pre = ""
+++

# Popping Up Cupcakes

Next we want to create a function to pop our cupcakes up out of the holes. There's CSS styling already set up for most of this so the cupcakes will appear with some pizazz, so we just need to add a class to one of our holes to make the cupcake appear. This will take the first hole from our list we saved earlier, and add the class of `up` to it (which will then do some CSS magic).

```js
function popUp() {
    let hole = holes[0];

    hole.classList.add('up');
}
```

Now instead of adding a comment in the console log at the start of the game, we can trigger our `popUp` function to run when the game starts. Under where you first defined your `startGame` function, remove the line about the console log and add the popUp function trigger.

**Note the different colours and +/- indicators in the code example below. This is instructing you to remove the `console.log` line, and add the `popUp` line.**

```diff
function startGame() {
-	console.log('Game has started');
+	popUp();

	setTimeout(endGame, 10000);
}
```

The resulting code should look like this:

```js
function startGame() {
    popUp();

    setTimeout(endGame, 10000);
}
```

Now try clicking the **Start** button and see what happens!
