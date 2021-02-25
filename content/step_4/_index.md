+++
title = "Step 4"
weight = 1
chapter = true
pre = ""
+++

# Ending the Game

Now it's time to use the `timeUp` variable that we saved earlier, editing the `endGame` function to set `timeUp` to be true.

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