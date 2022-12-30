1. JavaScript is single-threaded, which means that it can process instructions one instruction at a time.
2. The call stack stores the instructions that are being executed by the JavaScript interpreter.
3. Web APIs, such as setTimeout, do not get directly pushed into the call stack
4. Instead, they go through the callback queue.
5. When the call stack is empty, the browser takes a task from the callback queue and executes it.
6. The event loop is a task that keeps checking if there are any items in the callback queue and forwards them to the call stack but only when the call stack is empty.

https://www.youtube.com/watch?v=8aGhZQkoFbQ&ab_channel=JSConf