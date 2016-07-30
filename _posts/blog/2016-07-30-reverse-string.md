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

### Free Code Camp Basic Algorithm Scripting - Reverse a String

## Instruction:
Reverse the provided string.
You may need to turn the string into an array before you can reverse it.
Your result must be a string.

## Steps:
1. Create an empty string to hold the newly created string.
2. Create a FOR Loop in which the starting point is (str.length -1) which represents the last character of the string, and loops back the string. 
3. Return the reversed string.


```Javascript
function rev(str){
  var placeholder = '';
  for(var i = str.length -1; i >= 0; i--){
    placeholder += str[i];
  }
  return placeholder;
}
```