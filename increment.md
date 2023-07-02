The _prefix_ form `++counter` increments `counter` and returns the new value

```js
let y = 0;
console.log(++y); // 1
console.log(y) // 1
```

The _postfix_ form `counter++` also increments `counter` but returns the _old_ value (prior to increment)

```js
let x = 0;
console.log(x++); // 0
console.log(x); // 1
```