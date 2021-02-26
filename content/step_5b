+++
title = "6. What If..?"
weight = 6
chapter = true
pre = ""
+++

Now that we have got our cupcake bobbing in and out, we want to repeat this over and over again until the time is up. We're going to use one of the most useful and powerful bits of programming to do this - the `if` statement. We can use this to check a condition and take a different action depending on whether it is true or false. A typical `if` statement in JavaScript looks something like this: 

{{% notice note %}}
You don't need to copy this code!
{{% /notice %}}

```JS
if(condition == state) {
action
}
```

In our case, if the time we've allocated for our game (the value we set in the setTimeout line) is NOT false, our `if` statement should trigger `popUp` to run again. Here's what our updated code will look like:

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
Now when you hit 'Start' your cupcake will continually pop up and down - but it's doing it so fast (and on the same hole) that we can't see it moving! We'll fix this up in the next step by randomising which hole it pops up from.
