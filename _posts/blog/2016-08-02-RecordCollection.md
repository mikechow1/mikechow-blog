---
layout: post
title: Record Collection
excerpt: "Free Code Camp Checkpoint"
modified: 2016-08-02T14:17:25-04:00
categories: blog
tags: [FreeCodeCamp]
image:
  feature: so-simple-sample-image-7.jpg
  credit: Mariannizmo
  creditlink: http://mariannizmo.deviantart.com/art/FREE-5-Triangulation-Mosaic-backgrounds-406553032
comments: true
share: true
---

Free Code Camp Checkpoint - Record Collection

<u>Instruction:</u>

1. Write a function which takes an album's id (like 2548), a property prop (like "artist" or "tracks"), and a value (like "Addicted to Love") to modify the data in this collection.*

2. If prop isn't "tracks" and value isn't empty (""), update or set the value for that record album's property. Your function must always return the entire collection object.*

3. If prop is "tracks" but the album doesn't have a "tracks" property, create an empty array before adding the new value to the album's corresponding property.*

4. If prop is "tracks" and value isn't empty (""), push the value onto the end of the album's existing tracks array.*

5. If value is empty (""), delete the given prop property from the album.*

### Approaching the Problem
Expect to be stuck as FCC at first try. It's totally normal. Better to draw a dragram or a table or whatever before actual coding as the requirements here are hard to swollow at first.

You will need:
*if/else statments to check all 4 scenarios
*The [`Push()`] Method
*The [`delete`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete) Operator

### Steps
*Check if *value* is emptry.  If so, delete [id][prop] (e.g. 1)..
*If *value* isn't emtry, check if *prop* = *tracks*.
	*If *prop* isn't *tracks*, populate [id][prop] with the value (e.g. 2).
	*if *prop* is *tracks*, check if the *track* array is empty.
		*if yes: create an empty array for tracks prop, and update the array (e.g 3).
		*else: push the *value* in the existing array. (e.g. 4)

(e.g.1) updateRecords(2548, "artist", ""), artist should not be set
(e.g.2) updateRecords(5439, "artist", "ABBA"), artist should be "ABBA"
(e.g.3) updateRecords(1245, "tracks", "Addicted to Love"), tracks should have "Addicted to Love" as the last element.
(e.g.4) updateRecords(2468, "tracks", "Free"), tracks should have "1999" as the first element.		


```html
{% raw %}
// Only change code below this line
function updateRecords(id, prop, value) {
  if (value !== ""){
    if(prop !== "tracks"){
      collection[id][prop] = value;
    }else{
      if(!collection[id][prop]){
        collection[id][prop] = [];
      }
      collection[id][prop].push(value);
    }
  }else{
    delete collection[id][prop];
  }

  return collection;
}
{% endraw %}
```
