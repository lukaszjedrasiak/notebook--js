```javascript
new Promise((resolve, reject) => {
    resolve(); // will resolve the promise (.then(callback) will be called)

    reject(); // will fail the promise (.catch(callback) will be called)
});
```

Important - the first argument passed into Promise has to be `resolve`. You can't just put only reject `function`. If you want do that you need to pass 2 arguments, and the second is `reject`.

Rejecting with returned data
```javascript
const alwaysFail = () => {
    return new Promise((resolve, reject) => {
        reject("Failed. That's the only thing I do.")
    });
}

alwaysFail()
  .then(() => {
    // will never be called
  })
  .catch(data => {
    console.error(data); // "Failed. That's the only thing I do."
  });
```