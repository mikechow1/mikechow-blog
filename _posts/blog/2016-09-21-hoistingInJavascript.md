---
layout: post
title: Hoisting in Javascript
excerpt: "Javascript Notes"
modified: 2016-09-21T14:17:25-04:00
categories: blog
tags: [javascript]
image:
  feature: so-simple-sample-image-7.jpg
  credit: Mariannizmo
  creditlink: http://mariannizmo.deviantart.com/art/FREE-5-Triangulation-Mosaic-backgrounds-406553032
comments: true
share: true
---

Hoisting in Javascript

### WTF is hoisting?

When a var appears inside a scope, that declaration is taken to belong to the entire scope and accessible everywhere.

Consider:

```Javascript
{% raw %}   

var a = "hello world";
b();

function b(){
	a = 3;
	console.log(a);
	var a;
}

console.log(a);

{% endraw %}
```

So even though the function was below where it was executed, it still ran.

The reason JS behaves the ways it does, the variables and functions are to some degee available even though they're written later in the code, is because the execution context is created in two phases.

The 1st phase is called the creation phase. We have the global object which is set up within memory. We have "this" which is set up in memory.  There's an outer environments that's created.

In that creation phase, it recognizes where you've created variables and where you've created functions.  So it set up the memory space for the variables and functions.  And it's that step this is called hoisting.

What it means is before your code begins to be executed line by line, the JS engine has already set aside memory space for the variables you've created in that entire code you've built, and all of the functions. So those functions and variables exist in memory.  So when the code begins to execute line by line, it can access them.

However, when it comes to variables, it's a bit different.  In the execution phase where it actually executes your code line by line. So the JS engine when it sets up the memory space for <cite>a</cite>, it doesn't know what its value until it starts executing its code. So instead it puts a placeholder called `undefined`.

All variables in JS are initially set to undefined, and functions are set in memory in their entirety. 

So hoisting is where you can call the function even though it's declared later really has to do with the fact that what you wrote is not what's directly being executed but the Javascript engine is taking the code and making decisions. 

In the first phase of creating the execution context the wrapper around the code being executed, it's going to setup the memory space for the functions and the variables that it sees, that are going to be used when it starts executing the code.

So basically it's just phase one when it sets up the memory space. When the code begins executing, those things are actually already sitting in memory. It looked at your code and already preset things up to be ready for the code to start executing.



