## intro

The `.then(callback)` schedules the `callback` into the future when the promise completes successfully.

When a function returns a promise, you can call `.then(callback)` on its result. The callback will be scheduled in the future when the promise completes successfully.

Simple example
```javascript
console.log("A");
wait(1000).then(() => {
    console.log("B");
});
console.log("C");

// output:
// "A"
// "C"
// "B" -> 1 second later
```

Fetch emulator
```js
const init = () => {
    fakeFetch().then(() => {
        console.log("Fake fetch completed");
    })
}
```

Pseudocode
```js
fetchData('fromWhere')
	.then(fetchedThings => console.log(fetchedThings)) //promise resolved
	.catch(error => console.log(error)); //promise rejected
	.finally(() => console.log("end")) //execute no matter if fetching was successful or not
```

- A promise can have 3 states: `pending`, `fulfilled`, and `rejected`.
- Every promise starts with the `pending` state and then becomes `fulfilled` when it has been completed successfully.
- Promises let you run a callback sometime in the future when the promise has been completed successfully.