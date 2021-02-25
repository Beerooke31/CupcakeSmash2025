+++
title = "Step 5"
weight = 1
chapter = true
pre = ""
+++

# Popping the cupcake back up

We also need to get the cupcake to pop back down again, by removing the `up` class again. This time we're also going to pass our `hole` variable to the `popDown` function, so that it can remove the `up` class. Try changing the value of `time` and see what happens (this value is in milliseconds, so 500 milliseconds is 0.5 seconds).

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

We also want to repeat the cupcake popping up until the time is up, so if time isn't up, it will trigger `popUp` to run again.

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