When working with APIs (for example a service that returns the weather forecast), the result/response will take some time to come back. This is why we're learning about asynchronous JavaScript (a concept that we're explaining in the next few lessons/chapters).

## intro
`setTimeout(callback, milliseconds)` is a JavaScript function that queues the `callback` into the future (depending on the `milliseconds` you specify).

```javascript
setTimeout(() => {
    console.log("One second has elapsed.");
}, 1000);
```

## execution order
```javascript
console.log("A");
setTimeout(() => {
    console.log("B")
}, 1000);
console.log("C");
```