+++
title = "7. That's so Random"
weight = 7
chapter = true
pre = ""
+++

# Randomising the cupcakes

We obviously don't want the diamond to always pop up in the first hole, because that would make for a pretty boring (and easy) game! Instead we'll create a new function to randomly pick which hole the cucpcake will appear in.

At the moment our `popUp` function looks like this:

```js
function popUp() {
    console.log('Here I am!');
    let hole = holes[0];
    let time = 500;

    hole.classList.add('up');

    setTimeout(function () {
        hole.classList.remove('up');

        if (timeUp == false) {
            popUp();
        }
    }, time);
}
```

The part of this code that determines where the diamond pops up is this line:

```js
let hole = holes[0];
```

Remember right back at the start when we created our `holes` variable? We wrote a line that looked like:

`let holes = document.querySelectorAll('.hole');`

In that step we looked for every hole element on the page, and stored in this `holes`variable. The`[0]`in`holes[0]` is what tells JavaScript to just get the first hole on the page.

{{% notice tip %}}

Our `holes` variable type is called an '[array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)' and looks something like this: `holes = [hole 1, hole 2, hole 3, ... hole 9]`. We can reference any item in our array using the index position (what position it is in in the list). An important thing to know about arrays is that the first position is always '0' (not 1). So if we reference `holes[1]` it will actually access the second item, not the first!

{{% /notice %}}

Our goal is to randomly generate a number between 0 and 8 (because we have 9 holes) that we can use to reference one of the holes in our array, rather than always getting the first one. To do this we are going to create our own function called `randomHole` which will use JavaScript's built in [`math.floor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) and
the [`math.random`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) functions.

At the bottom of your existing code, add this:

```js
function randomHole(holes) {
    let holeNumber = Math.floor(Math.random() * holes.length);
    let hole = holes[holeNumber];

    return hole;
}
```

We then need to update our `popUp` function to run our new `randomHole` function each time the diamond pops up, instead of always referring to the first hole:

```diff
function popUp() {
-	let hole = holes[0];
+   let hole = randomHole(holes);
	let time = 500;

	hole.classList.add('up');

	setTimeout(function() {
		hole.classList.remove('up');

		if(timeUp == false) {
				popUp();
		}
	}, time)
}
```

Now when you hit **Start**, you should see your cupcakes popping up everywhere!

## Check your code!

This is what you should have in CodePen so far:

```js
let timeUp = false;
let holes = document.querySelectorAll('.hole');
let scoreBoard = document.querySelector('.score');

function startGame() {
    timeUp = false;
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
