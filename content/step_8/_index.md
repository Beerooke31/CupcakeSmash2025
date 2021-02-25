+++
title = "Step 8"
weight = 8
chapter = true
pre = ""
+++

# Randomising the Cupcakes

We also don't want the cupcake to always pop up in the first hole, so we need to create a new function to randomly pick one of the holes to appear in. To do this we need to randomly generate a number between 0 and the number of holes there are. Using that number, we can then reference the hole from in the list. At the bottom of your code, add this:

```js
function randomHole(holes) {
	let holeNumber = Math.floor(Math.random() * holes.length)
	let hole = holes[holeNumber]

	return hole
}
```

We then need to use the `randomHole` function each time the cupcake pops up, so that the cupcakes pop out of a different hole each time.

```diff
function popUp() {
-	let hole = holes[0]
+ let hole = randomHole(holes)
	let time = 500

	hole.classList.add('up')

	setTimeout(function() {
		hole.classList.remove('up')
	
		if(timeUp == false) {
				popUp()
		}
	}, time)
}
```