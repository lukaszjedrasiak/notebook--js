This method fill the array with the given value from the `start` index to the `end`. The `end` item is excluded from the method.

## syntax

```js
array.fill(value, [start], [end])
```

## example

```js
let a = new Array(5);

a.fill(0, 1, -2) // => a == [empty, 0, 0, 0, empty]
```
