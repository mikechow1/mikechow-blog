---
layout: post
title: Factorialize a Number
excerpt: "Free Code Camp Basic Algorithm Scripting"
modified: 2016-08-01T14:17:25-04:00
categories: blog
tags: [FreeCodeCamp]
image:
  feature: so-simple-sample-image-7.jpg
  credit: Mariannizmo
  creditlink: http://mariannizmo.deviantart.com/art/FREE-5-Triangulation-Mosaic-backgrounds-406553032
comments: true
share: true
---

Free Code Camp Basic Algorithm Scripting - Factorialize a Number

<u>Instruction:</u>

>Return the factorial of the provided integer.
>If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to n.
>Factorials are often represented with the shorthand notation n!
>For example: 5! = 1 * 2 * 3 * 4 * 5 = 120

## Using a For Loop

Steps:

* Start the FOR loop with i = 1.  Increment i for each iteration.
* We store the value of num at each iteration.


~~~ Javascript
function fact(num) {
	var result = 1;
	for (var i = 1; i<=num; i++){
		result *= i;
	}
  return result;
}
~~~

Ex: 5! = 1 * 2 * 3 * 4 * 5 = 120

| iteration | i   | result *= i | i <= 5? |
| 1st  	| 1   | 1 = 1 * 1   |   yes   |
| 2nd   	| 2   | 2 = 2 * 1   |   yes   |
| 3rd       | 3   | 6 = 3 * 2   |   yes   |
| 4th       | 4   | 24 = 4 * 6  |   yes   |
| 5th       | 5   | 120 = 5 * 24|   yes   |
| 6th       | 6   |             |   no    |
{: .table}

Result:
<cite>fact(5)</cite> should become 120.




