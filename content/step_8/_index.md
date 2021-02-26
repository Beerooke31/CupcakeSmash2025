+++
title = "7. That's so random"
weight = 7
chapter = true
pre = ""
+++

# Randomising the Cupcakes

We obviously don't want the cupcake to always pop up in the first hole, because that would make for a pretty boring (and easy) game! The next step is to create a new function to randomly pick one of the holes to appear in each time our `popUp` function runs. 

At the moment our popUp function looks like this:

```js
function popUp() {
	let hole = holes[0]
	let time = 500

	hole.classList.add('up')

  setTimeout(() => {
    hole.classList.remove('up');
		if(!timeUp) 
		popUp();
	
  }, time);
}
}
```

The part of this code that determines which hole the cupcake pops up in is this line:
```js
let hole = holes[0]
```

Remember right back at the start when we created our `holes` variable? In that step we created a list we could refer back to by counting the holes on the page. That list is stored as an [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) that looks like this:

holes = \[hole 1, hole 2, hole 3, ... hole 9]

We can reference any item in our array using the index position (what position it is in in the list).

{{% notice note %}}
An important thing to know about arrays is that the first position is always '0' (not 1). So if we reference `holes[1]` it will actually access the second item, not the first!
{{% /notice %}}

Our goal is to randomly generate a number between 0 and 8 (because we have 9 holes) that we can use to reference one of the holes in our array. To do this we are going to create our own function called `randomHole` which will use the [`math.floor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) function and 
the [`math.random`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) function combined with the length property (which simply counts the number of items in our array).

At the bottom of your existing code, add this:

```js
function randomHole(holes) {
	let holeNumber = Math.floor(Math.random() * holes.length)
	let hole = holes[holeNumber]

	return hole
}
```

We then need to update our `popUp` function to run our new `randomHole` function each time the cupcake pops up, instead of always referring to the first hole:

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

Now when you hit start, you should see your cupcakes popping up everywhere!
