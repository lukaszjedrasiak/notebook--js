This method **returns** a new array that contains the element specified by the first argument and all subsequent elements up to, but not including, the element specified by the second argument.

The second argument can get the following values:
- none: the slice consists all elements from starts to the end
- negative values: the position of the slice end is counting from the end, i.e. `-1` means the last element

> It doesn't modify the original array.

## syntax

```javascript
array.slice(start, [end])
```

## examples

```js
let a = [1, 2, 3, 4, 5]
a.slice(0, 3) // => [1, 2, 3]
a.slice(3) // => [4, 5]
a.slice(1, -1) // => [2, 3, 4, 5]
a.slice(-3, -2) // => [3]
```