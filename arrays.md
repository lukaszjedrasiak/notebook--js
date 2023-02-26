## creating arrays

### array literal
```js
let sampleArray = ['element example', 10, true];
```

## properties
- array.length

## methods

### adding elements

```javascript
array.push(element) // add element at the end of the array and return new length
```

```javascript
array.unshift(element) // add element at the beginning of the array and returns new length
```

### removing elements

```javascript
array.pop() // removes and returns the last item of the array
```

```javascript
array.shift() // removes and returns the first item of the array
```

### filtering

```javascript
array.slice(start, end) // returns a new array that contains the element specified by the first argument and all subsequent elements up to, but not including, the element specified by the second argument.
```

```javascript
array.IndexOf(element) // returns the array index of the given element
```

### iterators

Iterators are methods called on arrays to manipulate elements and return values.
> See also: [function callbacks](function-callbacks)

1. [forEach()](forEach) - is used to execute the same code on every element in an array but does not change the array and returns `undefined`
2. [map()](map) - executes the same code on every element in an array and returns a new array with the updated elements
3. [filter()](filter) - checks every element in an array to see if it meets certain criteria and returns a new array with the elements that return truthy for the criteria
4. [findIndex()](findIndex) - returns the index of the first element of an array that satisfies a condition in the callback function. It returns `-1` if none of the elements in the array satisfies the condition
5. [reduce()](reduce) - iterates through an array and takes the values of the elements and returns a single value
6. [every()](every) - Returns `true` when **every** item in the array satisfies the condition provided in the callback

TO DO:
[find()](find)
[some()](some)
[splice()](splice)
[includes()](includes)
[join()](join)

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

## misc
[[destructuring]]
[[concatenation]]
[array of objects](array-of-objects)

## references
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array