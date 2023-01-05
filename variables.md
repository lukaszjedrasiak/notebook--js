- `let` is the preferred way to declare a variable when it can be reassigned, and `const` is the preferred way to declare a variable with a constant value.
- [[var]] declaration can be treated as a legacy code.
- Variables that have not been initialized store the primitive data type `undefined`.
- in legacy mode (without [[use strict]]) you can declare and assign the variable without the keyword `let` or `const`, i.e. `num = 5`. In `use strict` mode it will prompt an error.

