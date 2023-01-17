Basic function
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

[[arrow functions]]

### Returning booleans
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

[[functions callbacks]]

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