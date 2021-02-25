+++
title = "Step 4"
weight = 1
chapter = true
pre = ""
+++

# Ending the Game

Before we go too much further with our cupcake shenanigans, let's edit the `endGame` function we created earlier so that instead of publishing a message to the console log, it changes the value stored in our `timeUp` variable to 'true.'

```diff
function endGame() {
-	console.log('Game has finished')
+	timeUp = true
}
```

We'll also need to make sure we set `timeUp` back to false when the game starts again.

```diff
function startGame() {
+	timeUp = false
	popUp()	

	setTimeout(endGame, 10000)
}
```
