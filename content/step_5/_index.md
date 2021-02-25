+++
title = "Step 5"
weight = 1
chapter = true
pre = ""
+++

# Popping the Cupcake Back Down

Now that we've got our cupcake jumping out of its hole, we also need to get the cupcake to pop back down again to make smashing it a little trickier! We do this by simply removing the `up` class we added earlier to our `popUp` function. 

We're also going to set a time for how long we want the `up` class to stay with our little cupcake. Try changing the value of `time` and see what happens (this value is in milliseconds, so 500 milliseconds is 0.5 seconds).

```diff
function popUp() {
	let hole = holes[0]
+	let time = 500

	hole.classList.add('up')

+	setTimeout(function() {
+		hole.classList.remove('up')
+ }, time)
}
```

Now that we have got our cupcake bobbing in and out, we want to repeat this over and over again until the time is up. We're going to use one of the most useful and powerful bits of programming to do this - the `if` statement. We can use this to check a condition and take a different action depending on whether it is true or false. A typical `if` statement in JavaScript looks something like this: (Note: you don't need to copy this code!)

```JS
if(condition == state) {
action
}
```

In our case, if the time we've allocated for our game (the value we set in the setTimeout line) is NOT false, our `if` statement should trigger `popUp` to run again.

```diff
function popUp() {
	let hole = holes[0]
	let time = 500

	hole.classList.add('up')

	setTimeout(function() {
		hole.classList.remove('up')

+		if(timeUp == false) {
+			popUp()
+		}

	}, time)
}
```
