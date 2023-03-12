## basic example

From Codecademy
```js
const executorFunction = (resolve, reject) => {  
  if (someCondition) {  
      resolve('I resolved!');  
  } else {  
      reject('I rejected!');  
  }  
}  
const myFirstPromise = new Promise(executorFunction);
```

## ...

```javascript
const waitOneSecond = () => {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve();
        }, 1000);
    });
}
```

```javascript
waitOneSecond().then(() => {
    console.log("Waited one second");
});
```

Example - wait promise
```javascript
const wait = milliseconds => {
    return new Promise(resolve => {
        setTimeout(() => {
	        const seconds = milliseconds / 1000;
            resolve(seconds);
        }, milliseconds);
    });
}


// Sample usage - do not modify
wait(1000).then((data) => {
    console.log(`Done waiting: ${data} seconds`);
});
```

When implementing a function that returns a promise, you have to `return new Promise(() => {})`.
The `() => {}` function inside the Promise constructor is called `executor`.
The executor receives as the first argument the `resolve` function. You should call the `resolve()` function when the promise needs to move from `pending` to `fulfilled`.

Calling `resolve()` with a certain value will make that value available in the `.then(callback)`.