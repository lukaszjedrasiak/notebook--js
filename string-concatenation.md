``` javascript
console.log( "2" + "2" ) // "22"
console.log( '1' + 2 ); // "12"
console.log(2 + 2 + '1' ); // "41" and not "221"
console.log('1' + 2 + 2); // "122" and not "14"
```

The binary `+` is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.

```js
console.log(6 - "2") // 4
```