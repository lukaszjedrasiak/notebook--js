1. You should avoid var and instead use let or const.
2. Variables defined with let/const are block-scoped, meaning that they are only accessible in the nearest set of opening and closing curly braces.
3. Variables defined with var are function scoped, meaning that they are accessible anywhere in the nearest function.

Hoisting in JavaScript is when the variables you define inside a function are moved to the top of the function. This happens every time you define a variable using var.