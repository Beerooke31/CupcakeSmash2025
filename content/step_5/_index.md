+++
title = "5. Don't Eat Me!"
weight = 5
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

{{% notice tip %}}
If your code doesn't work as expected, check your brackets! In JavaScript brackets should always have partners. This goes for parentheses(), square brackets[] and braces{}  - just count the left ones and make sure they all have a buddy.
{{% /notice %}}

<!---
recommend adding a link here about what different bracket types are used for. Blog post on She Codes?
-->
