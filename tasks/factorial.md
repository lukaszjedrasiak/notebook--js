```js
const factorial = num => {

  if (num === 1) {
    return 1
  } else {
    return num * factorial(num - 1)
  }
}
console.log(factorial(7))
```

Most beautiful syntax :)
```js
const factorial = x => (x === 0) || (x === 1) ? 1 : x * factorial(x-1);
```