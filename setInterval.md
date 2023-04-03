## example

```js
setInterval(() => {  
  alert('Are you paying attention???')  
}, 300000)
```

The `setInterval()` would call the `alert()` function and show a pop-up message of `'Are you paying attention???'` every `300000` milliseconds (or 5 minutes).

This function returns a value that can be used to terminate the interval 'loop'.
```js
let counter = 0;
let intervalId = setInterval(() => {
	console.log(`>> ${counter}`);
	counter++;
	
	if (counter === 5) {
	clearInterval(intervalId);
	console.log('>> end');
	}
}, 1000);


// to check, because the interval do not work as expected
```