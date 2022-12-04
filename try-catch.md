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

