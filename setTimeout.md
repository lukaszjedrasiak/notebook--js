With `setTimeout()` we can write code that tells our JavaScript program to wait a minimum amount of time before executing its callback function.

## example

```js
setTimeout(() => {
	console.log('Delay the printing of this string, please.');
}, 1000);
```

## syntax

```js
setTimeout(callback, miliseconds);
```