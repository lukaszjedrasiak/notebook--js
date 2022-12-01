## properties
- array.length

## methods
```javascript
array.push(element) // add element to the array and return new length
```

```javascript
array.forEach(callback) //iterate over each element of the array. Do not returns an array
```

```javascript
array.filter(callback) //RETURNS new array that contains some of the items from the original array, based on the condition specified in callback function. Return keyword is neccessary.
```

`.filter()` method always returns an array:
- if one item matches the condition: an array with single element
- if no items match the condition: empty array

```javascript
array.find(callback) // returns the first item that matches the condition specified in callback function. If no items were found, you will get back `undefined`.
```

`.find()` method always returns one value:
- if no items match the condition: `undefined` value
- if more items match the condition: only the first value

[.map()](map)
[every()](every)
[some()](some)
[splice()](splice)
[reduce()](reduce)

```javascript
array.includes(element) // returns `true` when that `item` exists in the array and `false` otherwise.
```


```javascript
array.join(delimiter) // returns a string of the array elements separated by the delimiter
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

## deleting all items
```js
array.length = 0;
```

[[destructuring]]
[[concatenation]]