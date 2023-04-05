## syntax

```js
str.codePointAt(position)
```

Returns a decimal number representing the code for the character at `position`.

## examples

```js
// different case letters have different codes 
alert( "Z".codePointAt(0) ); // 90
alert( "z".codePointAt(0) ); // 122
alert( "z".codePointAt(0).toString(16) ); // 7a (if we need a hexadecimal value)
```