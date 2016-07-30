---
layout: post
title: Reverse a String in JavaScript
excerpt: "Free Code Camp Basic Algorithm Scripting"
modified: 2016-07-30T14:17:25-04:00
categories: blog
tags: [FreeCodeCamp]
image:
  feature: so-simple-sample-image-7.jpg
  credit: Mariannizmo
  creditlink: http://mariannizmo.deviantart.com/art/FREE-5-Triangulation-Mosaic-backgrounds-406553032
comments: true
share: true
---

Free Code Camp Basic Algorithm Scripting - Reverse a String

<u>Instruction:</u>

>Reverse the provided string.
>You may need to turn the string into an array before you can reverse it. Your result must be a string.

## Using a For Loop

Steps:

* Create an empty string to hold the newly created string.
* Create a FOR Loop in which the starting point is (str.length -1) which represents the last character of the string, and loops back the string. 
* Return the reversed string.


```Javascript
function rev(str){
  var placeholder = '';
  for(var i = str.length -1; i >= 0; i--){
    placeholder += str[i];
  }
  return placeholder;
}
```

String "hello" length equals 5:

| iteration | i   | placeholder |
| 1st  	| 4   | "o"         |
| 2nd   	| 3   | "ol"        |
| 3rd       | 2   | "oll"       |
| 4th       | 1   | "olle"      |
| 5th       | 0   | "olleh"     |
{: .table}

Result:
<cite>rev("hello")</cite> should become "olleh"

## Using Built-in Functions

Steps:

* Use the Split() method to return a new array
* Use the Reverse() method to reverse the new array.
* Use the join() method to join all the splitted elements back into a string.
* Return the reversed string.


```Javascript

function rev(str){
	var reverseStr = str.split('').reverse().join("");
}

```

Resources:
[`split()` method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
[`reverse()` method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
[`join()` method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
[`String.length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)