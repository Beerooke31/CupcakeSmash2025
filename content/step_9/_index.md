+++
title = "Step 9"
weight = 9
chapter = true
pre = ""
+++

# Randomising the time

To properly mix everything up, we also want the cupcakes to stay up for a random period of time, rather than always for 500 milliseconds. This function will take a minimum and a maximum value, and randomly choose a number between the two. At the bottom of your code, add this:

```js
function randomTime(min, max) {
	let time = Math.round(Math.random() * (max - min) + min)

	return time
}
```

We can then use the `randomTime` function to randomly pick a time interval, we can choose the minimum and maximum amount of time a cupcake can stay up for.

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