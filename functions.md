A programming language is said to have **First-class functions** when functions in that language are treated like any other variable. For example, in such a language, a function:
- can be passed as an argument to other functions (the function that we pass as an argument to another function is called a _callback function_),
- can be returned by another function (A function that returns a function or takes other functions as arguments is called a _higher-order function_),
- can be assigned as a value to a variable.

---

Three ways of declaring functions:
1. function declaration
2. function expression
3. arrow function

> Variables passed to the function within parameters are *passed-by-reference*. It means that parameter is passing to the function a reference to where the variable memory is stored. It allows us to change (mutate) the original (global) variables.

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

## functions as values

JavaScript functions behave like any other data type in the language; we can assign functions to variables, and we can reassign them to new variables.

```js
const announceThatIAmDoingImportantWork = () => {  
    console.log("I’m doing very important work!");  
};

const busy = announceThatIAmDoingImportantWork;
busy(); // This function call barely takes any space!
```

`busy` is a variable that holds a _reference_ to our original function. If we could look up the address in memory of `busy` and the address in memory of `announceThatIAmDoingImportantWork` they would point to the same place. Our new `busy()` function can be invoked with parentheses as if that was the name we originally gave our function.

Notice how we assign `announceThatIAmDoingImportantWork` without parentheses as the value to the `busy` variable. We want to assign the value of the function itself, not the value it returns when invoked.

Since functions are a type of object, they have properties such as `.length` and `.name`, and methods such as `.toString()`.

```js
console.log(busy.name) //returns 'announceThatIAmDoingImportantWork'
```

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
[[function-callbacks]]
[return](return)