This method convert float number into **string** with given digits numbers after dot. Take a note that result is rounded.

```js
let n = 123456.789

n.toFixed(0) // => 123457
n.toFixed(2) // => 123456,79
n.toFixed(5) // => 123456,78900
```