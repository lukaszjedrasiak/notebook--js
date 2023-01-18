```javascript
//step 0
function sum(x, y) {
    return x + y;
}

// step 1
const sum = function (a, b) {
	return a + b;
}

// step 2
const sum = (a, b) => {
	return a + b; 
}
```

If there is only one argument, parentheses may be ommited:
```js
	const double = n => n * 2;
```

If there are no arguments, parenthese must be present:
```js
	const sayHi = () => console.log('Hi!');
```

One-line arrow functions do not need a `return` keyword. See more: [[implicit return]]

## Examples

```js
function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Do you agree?",
  () => alert("You agreed."),
  () => alert("You canceled the execution.")
);
```
