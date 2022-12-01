Basic arrow function
```javascript
const isLegal = (age) => {
    return age >= 18;
}
```

Arrow function with implicit return
```javascript
const isLegal = (age) => age >= 18;
```

The shortest form
```javascript
const isLegal = age => age >= 18;
```

Terms of use of the implicit return:
1.  Your function must be an arrow function.
2.  The function body must be only **one line**. This means you must remove the curly braces.
3.  You must remove the `return` keyword because the function body is one line.