---
layout: post
title: Check for Palindromes
excerpt: "Free Code Camp Basic Algorithm Scripting"
modified: 2016-08-03T14:17:25-04:00
categories: blog
tags: [FreeCodeCamp]
image:
  feature: so-simple-sample-image-7.jpg
  credit: Mariannizmo
  creditlink: http://mariannizmo.deviantart.com/art/FREE-5-Triangulation-Mosaic-backgrounds-406553032
comments: true
share: true
---

Free Code Camp Basic Algorithm Scripting - Check for Palindromes

<u>Instruction:</u>

>Return true if the given string is a palindrome. Otherwise, return false.

>A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.

### Approaching the Problem

Take a look at all the cases below which need to be satisied.  

```html
{% raw %}

palindrome("eye") should return a boolean.
palindrome("eye") should return true.
palindrome("_eye") should return true.
palindrome("race car") should return true.
palindrome("not a palindrome") should return false.
palindrome("A man, a plan, a canal. Panama") should return true.
palindrome("never odd or even") should return true.
palindrome("nope") should return false.
palindrome("almostomla") should return false.
palindrome("My age is 0, 0 si ega ym.") should return true.
palindrome("1 eye for of 1 eye.") should return false.
palindrome("0_0 (: /-\ :) 0-0") should return true.
palindrome("five|\_/|four") should return false.

{% endraw %}
```
I have been avoided using [Regular Expression](https://developer.mozilla.org/en/docs/Web/JavaScript/Guide/Regular_Expressions) like the plague but I guess we have no choices in this case.  

Regex we need to use in this situation:

* `\W`  Matches any non-word character. Equivalent to [^A-Za-z0-9_].
* `_`  For Matching "0_0 (: /-\ :) 0-0".
* `g`  For global search.

So the Regex we need is "/[\W_]/g"

I used this [site](https://regex101.com/#javascript) for checking my Regex.

### Requirements

* [`toLowerCase()`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase) method
* [`split()`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/String/split) method
* [`reverse()`](https://msdn.microsoft.com/en-us/library/3333858x(v=vs.94).aspx) method
* [`replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) method
* [`join()`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/join) method

### Steps

* Take care the capitalization issue by using the toLowerCase() method.
* Use the replace() method to remove space and punctuation.
* Use the split() method to chop a string object into sub strings.
* Reverse() method to reverse the sub string array.
* Finally a join() method to put back all array elements into a string.

```html
{% raw %}
function palindrome(str){
	return str.replace(/[\W_]/g, '').toLowerCase()===
	str.replace(/[\W_]/g, '').toLowerCase().split('').reverse().join('');
}


palindrome("My age is 0, 0 si ega ym.");
{% endraw %}
```