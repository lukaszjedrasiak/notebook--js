This method **returns** an array joined from the original array and elements given in the argument. It doesn't change the content of the original array.

## syntax

```js
array.concat(newArray)
```

## examples

```js
let a = [1, 2, 3];
let b = a.concat(4, 5) // b == [1, 2, 3, 4, 5]
let c = a.concat([4, 5], [6, 7]) // c == [1, 2, 3, 4, 5, 6, 7]
let d = a.concat(4, [5, [6, 7]]) // d == [1, 2, 3, 4, 5, [6, 7]]

console.log(a) // => [1, 2, 3]
```