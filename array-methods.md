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

### filtering / searching / sorting

1. [slice](slice) – returns a part of given array
2. [splice](splice) – used to remove or insert elements in the array. It modifies the original array.
3. indexOf – returns the index of the given element (searching from the beginning) or `-1` if is not found. The second optional argument is a start position.
4. lastIndexOf – returns the index of the given element (searching from the end) or `-1` if is not found. The second optional argument is a start position.
5. [includes()](includes) – returns `true` when that `item` exists in the array and `false` otherwise.
6. [sort](sort) – sorting the array items.
7. reverse – reverses the order of elements in an array.

## iterators

Iterators are methods called on arrays to manipulate elements and return values.
> See also: [function callbacks](function-callbacks)

1. [forEach()](forEach) – is used to execute the same code on every element in an array but does not change the array and returns `undefined`
2. [map()](map) – executes the same code on every element in an array and returns a new array with the updated elements
3. [filter()](filter) – checks every element in an array to see if it meets certain criteria and returns a new array with the elements that return truthy for the criteria
4. [find()](find) – returns the **value** of the first element of an array that satisfies a condition in the callback function. It returns `undefined` if none of the elements in the array satisfies the condition.
5. [findIndex()](findIndex) – returns the **index** of the first element of an array that satisfies a condition in the callback function. It returns `-1` if none of the elements in the array satisfies the condition
6. [reduce()](reduce) – iterates through an array and takes the values of the elements and returns a single value
7. reduceRight() – works similar to the `reduce` method but iterates over the array starting from the last item (the biggest index).
7. [every()](every) – Returns `true` when **every** item in the array satisfies the condition provided in the callback
8. [some()](some) – returns `true` when **at least one** item in the array satisfies the condition provided in the callback.

## others

1. [flat](flat) – flat nested arrays
2. [concat](concat) – join arrays
3. [fill](fill) – fill the array with given value
4. copyWithin – copy the slice of the given array to the different place in the same array.

## to do

[join()](join)