`return` can be used as a input validation.

```js
function displayObject(o) {
	if (!o) return; // leaves function if `o` is undefined or null
}
```