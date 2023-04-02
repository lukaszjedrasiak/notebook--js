[array methods](array-methods)
## creating arrays

### array literal

```js
let sampleArray = ['element example', 10, true];
```

### spread syntax

```js
let a = [1, 2, 3];
let b = [0, ...a, 4] // b == [0, 1, 2, 3, 4]
```

```js
let chars = "qwerty"
let charsArray = [...chars] // charsArray = ["q", "w", "e", "r", "t", "y"] 
```

### constructor

```js
let a = new Array(arrayLength);
```

### Array.of

```js
let a = Array.of(1, 2, 3) // a == [1, 2, 3]
```

### Array.from

Callback function may change the copied elements. It works similar to `map` function.

```js
let a = [1, 2, 3];
let b = Array.from(a, [callback]) // b == [1, 2, 3]
let c = Array.from(a, x => x * 2) // c == [2, 4, 6]
```

## properties

### length

```js
array.length = 0; // delete all items
```

## element access

bracket syntax
```javascript
array[1];
```

.at() syntax
```javascript
array.at(-1) //get last element
```

## deleting items

```js
array.length = 0; // array == []
```

```js
let a = [1, 2, 3];
delete a[1]; // a == [1, empty, 3]
a.length = 3;
```

## misc
[[destructuring]]
[[concatenation]]
[array of objects](array-of-objects)
[multidimensional arrays](multidimensional-arrays)

## references
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array