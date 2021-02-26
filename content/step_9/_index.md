+++
title = "10. So Unpredictable"
weight = 10
chapter = true
pre = ""
+++

# Randomising the time

To properly mix everything up so our game isn't too predictable, we also want the cupcakes to stay up for a random period of time rather than always for 500 milliseconds (or maybe 1000 if our random number generator picks the same cupcake twice). This function will take a minimum and a maximum value, and randomly choose a number between the two. At the bottom of your code, let's add a new function called `randomTime`:

```js
function randomTime(min, max) {
	let time = Math.round(Math.random() * (max - min) + min)

	return time
}
```

We can then use our `randomTime` function to randomly pick a time interval, once we specify the minimum and maximum amount of time a cupcake can stay up for. In the example below we've set the minimum as 200ms and the maximum as 1000ms (1 second). We're going to make some alterations to our existing `popUp` function:

```diff
function popUp() {
	let hole = randomHole(holes)
-	let time = 500
+	let time = randomTime(200, 1000)

	hole.classList.add('up')

	setTimeout(function() {
		hole.classList.remove('up')
	
		if(timeUp == false) {
				popUp()
		}
	}, time)
}
```

Now run your game again, and you should see the cupcakes are a lot less predictable!
