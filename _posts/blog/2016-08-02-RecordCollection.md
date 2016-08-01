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

### Approaching the Problem
Expect to be stuck at first try. It's normal. Better to draw a dragram or a table or whatever before actual coding as the requirements here are hard to swollow at first.  Once you have it in drawing, it's earier to tickle.

The question is really about testing your concepts on objects, properties, arrays, if/else statements and how to use the !== and ! operators.

### Requirements
* [`if/else`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/if...else) statments to check all 4 scenarios
* The `Push()` Method
* The [`delete`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete) Operator

### Steps
* Check if *value* is emptry.  If so, delete [id][prop] (e.g. 1).
* If *value* isn't emtry, check if *prop* = *tracks*.
	* If *prop* isn't *tracks*, populate [id][prop] with the value (e.g. 2).
	* if *prop* is *tracks*, check if the *track* array is empty.
		* if yes: create an empty array for tracks prop, and update the array (e.g 3).
		* else: push the *value* in the existing array. (e.g. 4)

### Test all 4 scenarios:
* (e.g.1) updateRecords(2548, "artist", ""), artist should not be set
* (e.g.2) updateRecords(5439, "artist", "ABBA"), artist should be "ABBA"
* (e.g.3) updateRecords(1245, "tracks", "Addicted to Love"), tracks should have "Addicted to Love" as the last element.
* (e.g.4) updateRecords(2468, "tracks", "Free"), tracks should have "1999" as the first element.		



{% raw %}
  // Setup
  var collection = {
      "2548": {
        "album": "Slippery When Wet",
        "artist": "Bon Jovi",
        "tracks": [ 
          "Let It Rock", 
          "You Give Love a Bad Name" 
        ]
      },
      "2468": {
        "album": "1999",
        "artist": "Prince",
        "tracks": [ 
          "1999", 
          "Little Red Corvette" 
        ]
      },
      "1245": {
        "artist": "Robert Palmer",
        "tracks": [ ]
      },
      "5439": {
        "album": "ABBA Gold"
      }
  };
  // Keep a copy of the collection for tests
  var collectionCopy = JSON.parse(JSON.stringify(collection));

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

  // Alter values below to test your code

  updateRecords(5439, "artist", "ABBA");
  }
{% endraw %}

