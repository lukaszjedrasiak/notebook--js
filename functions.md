Three ways of declaring functions:
1. function declaration
2. function expression
3. arrow function

## function declaration

```javascript
function sum(x, y) {
    return x + y;
}
```

Function with default parameters
```javascript
function sum(x = 0, y = 0) {
    return x + y;
}
```

**A Function Declaration can be called earlier than it is defined**, because is created when JavaScript is preparing to start the script and is visible everywhere in it.

## returning booleans

Standard shape
```javascript
function isPassing(grade) {
    if (grade >= 10) {
        return true;
    } else {
        return false;
    }
}
```

Shorter shape
```javascript
function isPassing(grade) {
    return grade >= 10;
}
```

## terminology

When a value is passed as a function parameter, it’s also called an argument.

In other words, to put these terms straight:
- A `parameter` is the variable listed inside the parentheses in the function declaration (it’s a declaration time term).
- An `argument` is the value that is passed to the function when it is called (it’s a call time term).

## naming a functions

Functions are actions. So their name is usually a verb. It should be brief, as accurate as possible and describe what the function does, so that someone reading the code gets an indication of what the function does:
- "show..." – show something
- "get…" – return a value,
- "calc…" – calculate something,
- "create…" – create something,
- "check…" – check something and return a boolean, etc.

## function expressions

Function in JS is a **value**. When we create the function with a name, we store a function body inside this name (variable). We can even show the function body by printing the variable without parentheses.

```js
let sum = function(x, y) {
	return x + y;
}

console.log(sum);
```

We can also copy a function from one variable to another one:
```js
let newSum = sum;
```

Function Expressions are created when the code execution reaches them, so it is impossible to call them before declaration.

## miscellaneus
[[arrow functions]]
[[functions callbacks]]