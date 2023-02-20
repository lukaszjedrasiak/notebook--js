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

## concise body

### parentheses

If there is only one argument, parentheses may be ommited:
```js
	const double = n => n * 2;
```

If there are no arguments, parenthese must be present:
```js
	const sayHi = () => console.log('Hi!');
```

### curly braces

A function body composed of a single-line block does not need curly braces. Without the curly braces, whatever that line evaluates will be automatically returned.

One-line arrow functions do not need a `return` keyword. See more: [[implicit return]]

```js
const plantNeedsWater = day => day === 'Wednesday' ? true : false;
```

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
