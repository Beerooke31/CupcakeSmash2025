+++
title = "9. Keeping Score"
weight = 9
chapter = true
pre = ""
+++

# Keeping Score

Now that we can catch our cupcakes, we want to be able to keep track of how many we've smashed!

To keep track of the score we're going to update the number in the scoreboard, which we set as a variable right at the start.

We're going to create another variable (this time called `score`) that starts at zero, and increases by one each time a cupcake is successfully smashed. We're also going to tell our `scoreBoard` variable to show `score` whenever it is increased. To update `scoreBoard` we will use the [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) property.

```diff
+ let score = 0;

function smash(cupcake) {
	console.log('smashed!');

	cupcake.parentNode.classList.remove('up');
+	score = score + 1;
+	scoreBoard.textContent = score;
}
```

Each time we restart the game, we also want to reset the score back to zero, so we can start again from scratch.

```diff
function startGame() {
	timeUp = false;
+ score = 0;
+ scoreBoard.textContent = score;

	popUp();

	setTimeout(endGame, 10000);
}
```

You can read more about the `textContent` property here:  
[textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)
