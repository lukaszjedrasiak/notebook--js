1. From an inner function, we are able to access variables from the outer function.
2. A closure is the combination of a function bundled together with its surrounding variables.
3. A closure has three scope chains:
	- Variables in their own scope (variables defined between the curly braces of a function).
	- Variables defined in the outer function's scope.
	- Variables defined in the global scope.

Closures are useful during working with **states** (or **flags** known from embedded programming). Lets assume that we need to run a function only once after button click. We should use a variable declared outside the function and change the value inside.

```javascript
// start with a variable (state) saying that the confetti is NOT shown yet
// this variable is defined in the global scope
let isConfettiShown = false;

const runBtn = document.querySelector("#run-btn");
runBtn.addEventListener("click", () => {
    if (isConfettiShown) {
        return false;
    }
    showConfetti(); //call a fictional function that shows the confetti
    isConfettiShown = true; // set the state variable as true
});
```