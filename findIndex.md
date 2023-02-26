## basic syntax

```js
const array = ['...'];

const foundIndex = array.findIndex(item => {
	return //condition for looking item here
})
```

## outputs

1. The index of the first array element that evaluates to `true` in the callback function
2. `-1` if there is no element in the array that satisfies the condition in the callback function

## example

```js
const jumbledNums = [123, 25, 78, 5, 9];  
  
const lessThanTen = jumbledNums.findIndex(num => {  
  return num < 10;  
});
```