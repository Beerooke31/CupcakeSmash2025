+++
title = "8. SMASH IT"
weight = 8
chapter = true
pre = ""
+++

# Smashing the cupcakes

Now that our cupcakes are merrily popping up and down, let's write a function to 'smash' them!

To do this, we're going to create another function called `smash` to run whenever a cupcake is clicked. When this happens, we also want to remove the `up` class from the hole the cupcake is in so that the smashed cupcake pops down again.

Add the following function to the bottom of your code:

```js
function smash(cupcake) {
    console.log('smashed!');

    cupcake.parentNode.classList.remove('up');
}
```

When we created the HTML code in the template, we actually already instructed the button to run this function when it is clicked (feel free to peek at the HTML code and see this for yourself). Press **Start** and start smashing cupcakes! Whenever you click a cupcake it will disappear again, and a message will appear in the console.

{{% notice tip %}}

You may have noticed that we're using this thing called a `parentNode`. Up until now, we have been referencing the hole elements in the HTML, but now we want to reference the cupcake itself. In our HTML, the cupcake that we click on is a 'child' of the hole it is popping up from, so the `.parentNode` part tells JavaScript to look for the hole that the cupcake is appearing from, rather than the cupcake itself.
You can read more about nodes and parent nodes [here](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode).

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

function smash(cupcake) {
    console.log('smashed!');

    cupcake.parentNode.classList.remove('up');
}
```
