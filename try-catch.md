You can embrace a piece of code that can fail with `try...catch` block. Thanks to it the overall code will not stop, even if the error occurs.

```javascript
console.log("Step 1");
try {
    nonExistentFunction();
} catch (error) {
    console.error(error); // Uncaught ReferenceError: nonExistentFunction is not defined
}
console.log("Step 2");
```

### Throw exceptions

It's also possible for you to throw an exception manually. For example, let's say you're writing a `sayHello` function that takes a `name` parameter. And, you do not want to allow other developers on this project (including yourself) to ever call this function without a `name` parameter.

Here's how you can do that:

```javascript
const sayHello = name => {
    if (!name) {
        throw new Error("name must be provided");
    }
    console.log(`Hello ${name}`);
}

sayHello("Sam"); // Hello Sam
```

### Recover from exceptions

It's also possible for you to recover from potential exceptions by wrapping the code with `try...catch`. Here's an example assuming the `sayHello` function that we defined above:

```javascript
console.log("Code before");
try {
    sayHello();
} catch (error) {
    console.error("Wrong usage for sayHello")
}
console.log("Code After");
```

The benefit here is that our code won't stop running because of the `throw new Error`. This is because we _catch_ the error with the `try...catch` statement.
