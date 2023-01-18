---
{"dg-publish":true,"permalink":"/languages/javascript/content/java-script-strings/"}
---

JavaScript strings work same as most languages aka python, java etc. but here are some important details worth knowing about them

___
## String Immutability

-  They are immutable so doing something like won't work
```Javascript
let a = "Bruh";
a[2] = 'a';
console.log(a);
```

-  The output will just be `Bruh` instead of `Brah` 

___
## String primitives and String objects

 -  Note that JavaScript distinguishes between `String` objects and [primitive string](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) values. (The same is true of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) and [`Numbers`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number).)
 -  String literals (denoted by double or single quotes) and strings returned from `String` calls in a non-constructor context (that is, called without using the [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) keyword) are primitive strings. In contexts where a method is to be invoked on a primitive string or a property lookup occurs, JavaScript will automatically wrap the string primitive and call the method or perform the property lookup on the wrapper object instead.
 ```Javascript

const strPrim = "foo"; // A literal is a string primitive
const strPrim2 = String(1); // Coerced into the string primitive "1"
const strPrim3 = String(true); // Coerced into the string primitive "true"
const strObj = new String(strPrim); // String with new returns a string wrapper object.

console.log(typeof strPrim); // "string"
console.log(typeof strPrim2); // "string"
console.log(typeof strPrim3); // "string"
console.log(typeof strObj); // "object"

```

-  String primitives and `String` objects also give different results when using [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval). Primitives passed to `eval` are treated as source code; `String` objects are treated as all other objects are, by returning the object. For example:
```Js

const s1 = "2 + 2"; // creates a string primitive
const s2 = new String("2 + 2"); // creates a String object
console.log(eval(s1)); // returns the number 4
console.log(eval(s2)); // returns the string "2 + 2"

```
-  For these reasons, the code may break when it encounters `String` objects when it expects a primitive string instead, although generally, authors need not worry about the distinction.
-  A `String` object can always be converted to its primitive counterpart with the [`valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf) method.
```Javascript

console.log(eval(s2.valueOf())); // returns the number 4

```

___

## JavaScript Template Literal
-  In essence they are same as Formatted strings found in Python 
- here's how you'd use them
``` JavaScript

const name = "Chris";
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris"

```

one minor unique thing about them which I haven't seen in any other language except Python (at least so far) is how they respect line breaks
so you can write sumn like this
```JavaScript

const output = `I like the song.
I gave it a score of 90%.`;
console.log(output);

/*
I like the song.
I gave it a score of 90%.
*/

```

whereas normally you'd write sumn like this

```JavaScript

const output = "I like the song.\nI gave it a score of 90%.";
console.log(output);

/*
I like the song.
I gave it a score of 90%.
*/

```

so the former just makes it more readable than the latter 

___ 

## String Methods

<table class="ws-table-all notranslate">
  <tbody><tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><a href="jsref_charat.asp">charAt()</a></td>
    <td>Returns the character at a specified index (position)</td>
  </tr>
  <tr>
    <td><a href="jsref_charcodeat.asp">charCodeAt()</a></td>
    <td>Returns the Unicode of the character at a specified index</td>
  </tr>
  <tr>
    <td><a href="jsref_concat_string.asp">concat()</a></td>
    <td>Returns two or more joined strings</td>
  </tr>
  <tr>
    <td><a href="jsref_constructor_string.asp">constructor</a></td>
    <td>Returns the string's constructor function</td>
  </tr>
  <tr>
    <td><a href="jsref_endswith.asp">endsWith()</a></td>
    <td>Returns if a string ends with a specified value</td>
  </tr>
  <tr>
    <td><a href="jsref_fromcharcode.asp">fromCharCode()</a></td>
    <td>Returns Unicode values as characters</td>
  </tr>
    <tr>
    <td><a href="jsref_includes.asp">includes()</a></td>
    <td>Returns if a string contains a specified value</td>
    </tr>
  <tr>
    <td><a href="jsref_indexof.asp">indexOf()</a></td>
    <td>Returns the index (position) of the first occurrence of a value in a string</td>
  </tr>
  <tr>
    <td><a href="jsref_lastindexof.asp">lastIndexOf()</a></td>
    <td>Returns the index (position) of the last occurrence of a value in a string</td>
  </tr>
  <tr>
    <td><a href="jsref_length_string.asp">length</a></td>
    <td>Returns the length of a string</td>
  </tr>
  <tr>
    <td><a href="jsref_localecompare.asp">localeCompare()</a></td>
    <td>Compares two strings in the current locale</td>
  </tr>
  <tr>
    <td><a href="jsref_match.asp">match()</a></td>
    <td>Searches a string for a value, or a regular expression, and returns the matches</td>
  </tr>
  <tr>
    <td><a href="jsref_prototype_string.asp">prototype</a></td>
    <td>Allows you to add properties and methods to an object</td>
  </tr>
    <tr>
    <td><a href="jsref_repeat.asp">repeat()</a></td>
    <td>Returns a new string with a number of copies of a string</td>
    </tr>
  <tr>
    <td><a href="jsref_replace.asp">replace()</a></td>
    <td>Searches a string for a value, or a regular expression, and returns a string where the values are replaced</td>
  </tr>
  <tr>
    <td><a href="jsref_search.asp">search()</a></td>
    <td>Searches a string for a value, or regular expression, and returns the index (position) of the match</td>
  </tr>
  <tr>
    <td><a href="jsref_slice_string.asp">slice()</a></td>
    <td>Extracts a part of a string and returns a new string</td>
  </tr>
    <tr>
    <td><a href="jsref_split.asp">split()</a></td>
    <td>Splits a string into an array of substrings</td>
    </tr>
  <tr>
    <td><a href="jsref_startswith.asp">startsWith()</a></td>
    <td>Checks whether a string begins with specified characters</td>
  </tr>
  <tr>
    <td><a href="jsref_substr.asp">substr()</a></td>
    <td>Extracts a number of characters from a string, from a start index (position)</td>
  </tr>
  <tr>
    <td><a href="jsref_substring.asp">substring()</a></td>
    <td>Extracts characters from a string, between two specified indices (positions)</td>
  </tr>
  <tr>
    <td><a href="jsref_tolocalelowercase.asp">toLocaleLowerCase()</a></td>
    <td>Returns a string converted to lowercase letters, using the host's locale</td>
  </tr>
  <tr>
    <td><a href="jsref_tolocaleuppercase.asp">toLocaleUpperCase()</a></td>
    <td>Returns a string converted to uppercase letters, using the host's locale</td>
  </tr>
  <tr>
    <td><a href="jsref_tolowercase.asp">toLowerCase()</a></td>
    <td>Returns a string converted to lowercase letters</td>
  </tr>
  <tr>
    <td><a href="jsref_tostring_string.asp">toString()</a></td>
    <td>Returns a string or a string object as a string</td>
  </tr>
  <tr>
    <td><a href="jsref_touppercase.asp">toUpperCase()</a></td>
    <td>Returns a string converted to uppercase letters</td>
  </tr>
  <tr>
    <td><a href="jsref_trim_string.asp">trim()</a></td>
    <td>Returns a string with removed whitespaces</td>
  </tr>
  <tr>
    <td><a href="jsref_string_trim_end.asp">trimEnd()</a></td>
    <td>Returns a string with removed whitespaces from the end</td>
  </tr>
  <tr>
    <td><a href="jsref_string_trim_start.asp">trimStart()</a></td>
    <td>Returns a string with removed whitespaces from the start</td>
  </tr>
  <tr>
    <td><a href="jsref_valueof_string.asp">valueOf()</a></td>
    <td>Returns the primitive value of a string or a string object</td>
  </tr>
</tbody></table>

> [!attention]
> All string methods return a new value so the original variable remains unchanged
   

___

