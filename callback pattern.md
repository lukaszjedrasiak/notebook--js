The callback pattern is a programming pattern where you pass a function definition as a parameter to a function. That callback will then be automatically called once the function call has been completed successfully.

We have callbacks (and later promises) as they allow the browser to continue responding to user input instead of blocking and waiting until a function has finished executing.

```javascript
welcomeUser("Sam", () => {
    console.log("Done welcoming user");
});
```

We're only learning about the callback pattern because we'd like to replace it with promises in the next chapter.