The meaning of `undefined` is “value is not assigned”.

Normally, one uses [[null]] to assign an “empty” or “unknown” value to a variable, while `undefined` is reserved as a default initial value for unassigned things.

Technically, it is possible to explicitly assign `undefined` to a variable, but it is not recommended.

```js
let age = 100;
age = undefined;
console.log(age) // undefined
```

`undefined` is a global constant assigned to undefined variable.