This method sorts the items in given array.

## syntax

```js
array.sort([callback])
```

As default this method sorts items alphabeticaly. If we need to change the method we use the callback function with 2 arguments (a, b):
- **ascending** – if `a` must be before `b` the function must returns value < 0 (a-b);
- **descending** – if `a` must be after `b` the function must returns value > 0 (b-a).

## examples

```js
let a = [33, 4, 1111, 222]

a.sort((a, b) => a - b) // => [4, 33, 222, 1111]
a.sort((a, b) => b - a) // => [1111, 222, 33, 4]
```