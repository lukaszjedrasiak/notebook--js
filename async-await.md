## overview

- The `async/await` keywords are syntactic sugar on top of promises. Their goal is to make your code easier to read (and write).
- Learning promises is a pre-requisite to understanding `async/await`.
- The `async` keyword wraps the return value of the function with a promise. It's very important to know that when a function is `async` it means that it will **always return a promise**.
- An `async function` is a function defined with the `function` keyword.
- Class methods can be made `async` by prefixing the method name with the keyword `async`.

## async

The `async` keyword is used to write functions that handle asynchronous actions. We wrap our asynchronous logic inside a function prepended with the `async` keyword. Then, we invoke that function.

```js
async function myFunc() {  
  // Function body here  
};  
  
myFunc();
```

```js
const myFunc = async () => {  
  // Function body here  
};  
  
myFunc();
```

### example

```js
const withAsync = async(num) => {
    if (num === 0){
      return 'zero';
    } else {
      return 'not zero';
    }
}

withAsync(100)
  .then((resolveValue) => {
  console.log(` withAsync(100) returned a promise which resolved to: ${resolveValue}.`);
})
```

## await

`await` works only within `async` function.

The `await` keyword "pauses" the execution of a function, until the promise resolves. And, then, it will automatically resolve it (call `.then()` on it), and give you the `result` which you can save in a variable.

Whenever you use `await`, it means that you're working with a promise that needs to be resolved somewhere in the future. This means that the current function cannot return a value immediately and has to return a promise itself.

## chaining

Example
```js
const makeBeans = async () => {
  const type = await shopForBeans();
  const isSoft = await soakTheBeans(type);
  const dinner = await cookTheBeans(isSoft);
  console.log(dinner);
}

makeBeans();
```

## debugging

With `async...await`, we use `try...catch` statements for error handling. By using this syntax, not only are we able to handle errors in the same way we do with synchronous code, but we can also catch both synchronous and asynchronous errors. This makes for easier debugging!

```js
async function usingTryCatch() {  
try {  
   let resolveValue = await asyncFunction('thing that will fail');  
   let secondValue = await secondAsyncFunction(resolveValue);  
} catch (err) {  
   // Catches any errors in the try block  
   console.log(err);  
}  
}  
  
usingTryCatch();
```

## handling independent promises

Remember that `await` halts the execution of our `async` function. This allows us to conveniently write synchronous-style code to handle dependent promises. But what if our `async` function contains multiple promises which are not dependent on the results of one another to execute?

```js
async function waiting() {
	const firstValue = await firstAsyncThing(); 
	const secondValue = await secondAsyncThing();
	console.log(firstValue, secondValue);
}

async function concurrent() {
	const firstPromise = firstAsyncThing();
	const secondPromise = secondAsyncThing();
	console.log(await firstPromise, await secondPromise);
}
```

In the `waiting()` function, we pause our function until the first promise resolves, then we construct the second promise. Once that resolves, we print both resolved values to the console.

In our `concurrent()` function, both promises are constructed without using `await`. We then `await` each of their resolutions to print them to the console.

With our `concurrent()` function both promises’ asynchronous operations can be run simultaneously. If possible, we want to get started on each asynchronous operation as soon as possible! Within our `async` functions we should still take advantage of _concurrency_, the ability to perform asynchronous actions at the same time.

Note: if we have multiple truly independent promises that we would like to execute fully in parallel, we must use individual `.then()` functions and avoid halting our execution with `await`.

Another way to take advantage of concurrency when we have multiple promises which can be executed simultaneously is to `await` a `Promise.all()`.

We can pass an array of promises as the argument to `Promise.all()`, and it will return a single promise. This promise will resolve when all of the promises in the argument array have resolved. This promise’s resolve value will be an array containing the resolved values of each promise from the argument array.

```js
async function asyncPromAll() {
	const resultArray = await Promise.all([asyncTask1(), asyncTask2(), asyncTask3(), asyncTask4()]);
	for (let i = 0; i<resultArray.length; i++){
		console.log(resultArray[i]);
	}}
```

In our above example, we `await` the resolution of a `Promise.all()`. This `Promise.all()` was invoked with an argument array containing four promises (returned from required-in functions). Next, we loop through our `resultArray`, and log each item to the console. The first element in `resultArray` is the resolved value of the `asyncTask1()` promise, the second is the value of the `asyncTask2()` promise, and so on.

`Promise.all()` allows us to take advantage of asynchronicity— each of the four asynchronous tasks can process concurrently. `Promise.all()` also has the benefit of _failing fast_, meaning it won’t wait for the rest of the asynchronous actions to complete once any one has rejected. As soon as the first promise in the array rejects, the promise returned from `Promise.all()` will reject with that reason. As it was when working with native promises, `Promise.all()` is a good choice if multiple asynchronous tasks are all required, but none must wait for any other before executing.