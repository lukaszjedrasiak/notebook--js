## basic syntax

```js
array.reduce(reducer(accumulator, current), initialValue); //return the single value - result of reducer function iterating over each item
```
Used to calculate a single value from an array. Method takes a reducer which allows you to configure the logic of how the array will be reduced into a single number.

Usage
- summing the array items
- multiply the array items

## example

```javascript
const grades = [10, 15, 5];

const sum = grades.reduce((total, current) => { 
    return total + current;
}, 0);
```

