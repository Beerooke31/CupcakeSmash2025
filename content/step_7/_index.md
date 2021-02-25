+++
title = "Step 7"
weight = 7
chapter = true
pre = ""
+++

# Keeping Score

We also need to keep track of how many cupcakes we've smashed, so we need to keep track of the score, and update the scoreboard (which we saved in a variable earlier).

```diff
+ let score = 0

function smash(cupcake) {
	console.log('smashed!')

	cupcake.parentNode.classList.remove('up')
+	score = score + 1
+	scoreBoard.textContent = score
}
```

Each time we restart the game, we also want to reset the score, so we can start again from scratch.

```diff
function startGame() {
	timeUp = false
+ score = 0
+ scoreBoard.textContent = score

	popUp()
	
	setTimeout(endGame, 10000)
}
```