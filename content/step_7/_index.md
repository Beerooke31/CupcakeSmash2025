+++
title = "9. Keeping Score"
weight = 9
chapter = true
pre = ""
+++

# Keeping Score

Now that we can catch our diamonds, we want to be able to keep track of how many we've smashed!

To keep track of the score we're going to update the number in the scoreboard, which we set as a variable right at the start.

We're going to create another variable (this time called `score`) that starts at zero, and increases by one each time a diamond is successfully smashed.

```diff
let scoreBoard = document.querySelector('.score');
+ let score = 0;

function smash(diamond) {
	console.log('smashed!');

	diamond.parentNode.classList.remove('up');
+	score = score + 1;
}
```

We're also going to tell our `scoreBoard` variable to show `score` whenever it is increased. To update `scoreBoard` we will use the [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) property.

```diff
function smash(diamond) {
	console.log('smashed!');

	diamond.parentNode.classList.remove('up');
	score = score + 1;
+	scoreBoard.textContent = score;
}
```

**Start** the game and watch your score increase everytime you smash a diamond!

Each time we restart the game, we also want to reset the score back to zero, so we can start again from scratch.

```diff
function startGame() {
	timeUp = false;
+   score = 0;
+   scoreBoard.textContent = score;

	popUp();

	setTimeout(endGame, 10000);
}
```

Now each time you click **Start** you should see the score reset to zero.

## Check your code!

This is what you should have in CodePen so far:

```js
let timeUp = false;
let holes = document.querySelectorAll('.hole');
let scoreBoard = document.querySelector('.score');
let score = 0;

function startGame() {
    timeUp = false;
    score = 0;
    scoreBoard.textContent = score;
    popUp();

    setTimeout(endGame, 10000);
}

function endGame() {
    timeUp = true;
}

function popUp() {
    console.log('Here I am!');
    let hole = randomHole(holes);
    let time = 500;

    hole.classList.add('up');

    setTimeout(function () {
        hole.classList.remove('up');

        if (timeUp == false) {
            popUp();
        }
    }, time);
}

function randomHole(holes) {
    let holeNumber = Math.floor(Math.random() * holes.length);
    let hole = holes[holeNumber];

    return hole;
}

function smash(diamond) {
    console.log('smashed!');

    diamond.parentNode.classList.remove('up');
    score = score + 1;
    scoreBoard.textContent = score;
}
```
