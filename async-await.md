## overview
- The `async/await` keywords are syntactic sugar on top of promises. Their goal is to make your code easier to read (and write).
- Learning promises is a pre-requisite to understanding `async/await`.
- The `async` keyword wraps the return value of the function with a promise. It's very important to know that when a function is `async` it means that it will **always return a promise**.
- An `async function` is a function defined with the `function` keyword.
- `const X = async () => { ... }` is an `async arrow function`.
- Class methods can be made `async` by prefixing the method name with the keyword `async`.

## await
The `await` keyword "pauses" the execution of a function, until the promise resolves. And, then, it will automatically resolve it (call `.then()` on it), and give you the `result` which you can save in a variable.

The `await` keyword "pauses" the execution of a function, until the promise resolves. And, then, it will automatically resolve it (call `.then()` on it), and give you the `result` which you can save in a variable.

Whenever you use `await`, it means that you're working with a promise that needs to be resolved somewhere in the future. This means that the current function cannot return a value immediately and has to return a promise itself.
