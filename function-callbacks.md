## Basic syntax

```javascript
array.forEach(function(element) {
	//do something with each element of the array
	console.log(element);
})
```

## beforehand function

```js
function doSth(element) {
	//do something with given element
	console.log(element);
}

array.forEach(doSth);
```

## arrow function

```js
array.forEach(element => {
	//do sth with each element
	console.log(element);
})
```

JavaScript will take your callback function and call it for every single item in the array.

[[asynchronous callback]]
[[callback pattern]]