```js
const factorial = num => {

  if (num === 1) {
    return 1
  } else {
    return num * factorial(num - 1)
  }
}
console.log(factorial(7))
```

Most beautiful syntax :)
```js
const factorial = x => (x <= 0) ? 1 : x * factorial(x-1);
```

Syntax with edge case
```js
function factorial(x) {
	if (x < 0) throw new Error('x can not be smaller than 0')
	
	let f;
	for (f = 1; x > 1; f *= x, x--) /*empty body */;
	return f;
}
```