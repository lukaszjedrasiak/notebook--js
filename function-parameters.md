If function is called with less arguments than mentioned in declaration, the default or `undefined` values are assigned to the rest.

## rest parameter

The rest parameter has to be the last parameter in function declaration. The arguments in function call are first assigned to the explicit parameters, and the 'rest' is stored in the `rest` parameter.

This function can be called with any number of arguments. It returns the biggest of them.
```js
function max(first = -Infinity, ...rest) {
	let maxValue = first;
	for (let n of rest) {
		if (n > maxValue) {
			maxValue = n;
		}
	}
	return maxValue;
}

max(1, 10, 200, 2, 3, 2000, 4, 5, 6) // => 2000
```