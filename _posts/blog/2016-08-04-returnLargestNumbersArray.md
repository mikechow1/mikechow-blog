---
layout: post
title: Return Largest Numbers in Arrays
excerpt: "Free Code Camp Basic Algorithm Scripting"
modified: 2016-08-04T14:17:25-04:00
categories: blog
tags: [FreeCodeCamp]
image:
  feature: so-simple-sample-image-7.jpg
  credit: Mariannizmo
  creditlink: http://mariannizmo.deviantart.com/art/FREE-5-Triangulation-Mosaic-backgrounds-406553032
comments: true
share: true
---

Free Code Camp Basic Algorithm Scripting - Return Largest Numbers in Arrays

### Game Plan

This is basically about creating a set of nested FOR loops for a [`muit-dimensional array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections). I'm not really happy with most of the explainations out there regarding nested for loops which can be a massive confusion for beginners.  So lets loop through an example to illustrate.

```html
{% raw %}   

var arr = [
 [4, 5, 1, 3],
 [13, 27, 18, 26],    
 [32, 35, 37, 39],
 [1000,1001,857,1]
];

for(var i = 0; i < arr.length; i++) {
    var arr1 = arr[i];
    for(var j = 0; j < arr1.length; j++) {
        console.log("i: " + i + " j: " + j + " = " + arr1[j]);
    }
}

{% endraw %}
```
The output of the above:

```html
{% raw %} 

i: 0 j: 0 = 4
i: 0 j: 1 = 5
i: 0 j: 2 = 1
i: 0 j: 3 = 3
i: 1 j: 0 = 13
i: 1 j: 1 = 27
i: 1 j: 2 = 18
i: 1 j: 3 = 26
i: 2 j: 0 = 32
i: 2 j: 1 = 35
i: 2 j: 2 = 37
i: 2 j: 3 = 39
i: 3 j: 0 = 1000
i: 3 j: 1 = 1001
i: 3 j: 2 = 857
i: 3 j: 3 = 1

{% endraw %}
```

So base on the example above we can evaulate all the numbers with each of the four arrays to determine the largest.  

### Steps

* Create an empty array to hold the outcome.
* Nested For loops to iterate through the 1st and 2nd layers of the arrays.
* Initial a variable to hold the largest numbers in an array.
* `if statement` to assign new value to the <cite>largest</cite> variable.
* Populate the newly created empty array with the results and return it.

```html
{% raw %} 

function largestOfFour(arr){
	//create an empty array
	var max1 = [];
	//nested for loops
	for(var i=0; i<arr.length; i++){
		//initial a variable that will hold the largest number in an array
		var largest = 0;
		for(j=0; j < arr[i].length; j++){
		if(arr[i][j] > largest){
			largest = arr[i][j];
		}
		}
		max1[i]=largest;
	}
	return max1;
}

largestOfFour([[33,34],[922,2],[34,922,4444]]);

{% endraw %}
```
