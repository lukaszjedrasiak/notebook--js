- `let` is the preferred way to declare a variable when it can be reassigned, and `const` is the preferred way to declare a variable with a constant value.
- [[var]] declaration can be treated as a legacy code.
- Variables that have not been initialized store the primitive data type `undefined`.
- in legacy mode (without [[use strict]]) you can declare and assign the variable without the keyword `let` or `const`, i.e. `num = 5`. In `use strict` mode it will prompt an error.

## scope

Terms:
- **Scope** refers to where variables can be accessed throughout the program, and is determined by where and how they are declared.
- **Blocks** are statements that exist within curly braces `{}`.
- **Global scope** refers to the context within which variables are accessible to every part of the program.
- **Global variables** are variables that exist within global scope.
- **Block scope** refers to the context within which variables are accessible only within the block they are defined.
- **Local variables** are variables that exist within block scope.
- **Global namespace** is the space in our code that contains globally scoped information.
- **Scope pollution** is when too many variables exist in a namespace or variable names are reused.

In order to prevent *scope pollution* try to avoid declaring global variables when it is not necessary.

The following snippet is correct but can be misleading, because we have two variables with the same name, but with different scopes.

```js
const satellite = 'The Moon';
const galaxy = 'The Milky Way';
let stars = 'North Star';

const callMyNightSky = () => {
	const stars = 'Sirius';
	return 'Night Sky: ' + satellite + ', ' + stars + ', ' + galaxy;

};

console.log(callMyNightSky());
console.log(stars);
```
