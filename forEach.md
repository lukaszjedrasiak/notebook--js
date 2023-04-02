This method iterates over each element of an array and call a callback function over each of them. The callback function is a first argument of `forEach` method.

## basic syntax

```javascript
array.forEach(callback) //iterate over each element of the array. Do not returns an array
```

This callback function can have three arguments:
- value of the element;
- index of the element;
- an array itself.

## examples

```js
const fruits = ['mango', 'papaya', 'pineapple', 'apple'];
// Iterate over fruits below
fruits.forEach(fruit => console.log(`I want to eat a ${fruit}`))
```

```js
let data = [1,2,3,4,5];
let sum = 0;

data.forEach(value => sum += value);
```

```js
let data = [1, 2, 3, 4, 5];
// Incrementing the value of each element.
data.forEach((value, index, array) => array[index] = value + 1);
```