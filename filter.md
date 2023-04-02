The callback function must be a predicate – it has to return `true` or `false`. If given element match the condition (the result is true) it is assigned to the returned array.

In other words, `.filter()` method always returns an array:
- if one item matches the condition: an array with single element
- if no items match the condition: empty array

## basic syntax

```javascript
array.filter(callback) //RETURNS new array that contains some of the items from the original array, based on the condition specified in callback function. Return keyword is neccessary.
```

The callback function accepts two arguments:
- the value of each element;
- the index of element.

## examples

```js
const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door'];
const shortWords = words.filter(word => word.length < 6);
```

```js
let a = [5, 4, 3, 2, 1];
// returns the values under even indexes: 0, 2, 4 ...
let evens = a.filter((value, index) => index % 2 === 0);
```