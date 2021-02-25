+++
title = "Step 2"
weight = 1
chapter = true
pre = ""
+++

# Setting Up

To start off, we're going to grab some of the elements on the page, and save them in a variable so we can access them easily later, using the [`querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) and [`querySelectorAll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll) functions. These use CSS selectors so they're easy to reference HTML elements, where `querySelector` will fetch the first element that matches the selector, and `querySelectorAll` will fetch all of them, and give you back a list.

```js
let holes = document.querySelectorAll('.hole');
let scoreBoard = document.querySelector('.score');
```

We're also going to define another variable that we'll be using later, `timeUp`, which we'll use to stop the game at the end of the allotted time.

```js
let timeUp = false
```

Next we're going to create a function to run when someone clicks the **Start** button. We are going to call the function `startGame`. For now we're going to log to the console when the day has started, and then use the `[setTimeout`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) method to run another function, after a delay.

```js
function startGame() {
	console.log('Game has started')
	
	setTimeout(endGame, 10000)
}
```

Note: if you want to change the name of the function, make sure you edit the HTML so the button on line 2 runs the right function

We also need to define the `endGame` function, to finish the game after the timeout

```js
function endGame() {
	console.log('Game has finished')
}
```

In the bottom left corner of your Codepen, click on **Console** to open the console. Try clicking the **Start** button and wait a minute .and see what happens.

![](images/console_screenshot.png)