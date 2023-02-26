## basic syntax

``` javascript
array.every(callback);
```

Returns `true` when **every** item in the array satisfies the condition provided in the callback.

## example

```js
array.every(item => {
	return item === value;
})
```