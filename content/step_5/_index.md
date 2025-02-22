---
title = "5. Can't Catch Me!"
weight = 5
chapter = true
pre = ""
---

# Popping the cupcake Back Down

Now that we've got our cupcake jumping out of its hole, we also need to get the cupcake to pop back down again to make smashing it a little trickier! We do this by simply removing the `up` class we added earlier to our `popUp` function.

```diff
function popUp() {
	let hole = holes[0];
	hole.classList.add('up');
+	hole.classList.remove('up');
}
```

Press **Start**, what happens? Did you see it appear? Our code is running a little too fast for us to see! The cupcake is appearing and then immediately disappearing again, let's slow things down.

We're going to set a time for how long we want the `up` class to stay with our cupcake.

```diff
function popUp() {
	let hole = holes[0];
+	let time = 500;

	hole.classList.add('up');

+	setTimeout(function() {
		hole.classList.remove('up');
+ }, time)
}
```

You should now be able to see the cupcake appearing and disappearing when you start the game.

Try changing the value of `time` and see what happens (this value is in milliseconds, so 500 milliseconds is 0.5 seconds).

{{% notice tip %}}

If your code doesn't work as expected, check your brackets! In JavaScript brackets should always have partners. This goes for parentheses(), square brackets[] and braces{} - just count the left ones and make sure they all have a buddy.

{{% /notice %}}

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
    let hole = holes[0];
    let time = 500;

    hole.classList.add('up');

    setTimeout(function () {
        hole.classList.remove('up');
    }, time);
}
```
