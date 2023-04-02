## syntax

```js
array.flat(level)
```

## examples

```js
let a = [1, [2, [3, [4]]]];

a.flat(1) // [1, 2, [3, [4]]]
a.flat(2) // [1, 2, 3, [4]]
a.flat(3) // [1, 2, 3, 4]
a.flat(4) // [1, 2, 3, 4]
```