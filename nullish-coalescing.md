It returns first `defined` value in the chain (not `null` or `undefined`).

```js
let user;
console.log(user ?? 'Anonymous'); // Anonymous

let user = 'John';
console.log(user ?? 'Anonymous'); // Johb
```

The nullish coalescing operator `??` provides a short way to choose the first “defined” value from a list, instead of displaying "null" or "undefined". This operator is useful to avoid showing `undefined` or `null` to the User Interface, which are often signs of bugs.

We can rewrite result = a ?? b using the operators that we already know, like this:
```js
result = (a !== null && a !== undefined) ? a : b;
```

nullish coalescing with the optional chaining
```javascript
const name = user.details?.name?.firstName ?? "N/A";
```

Nullish coalescing has lower precedence than such operators like `+` or `-`. So you need to wrap the operator with curly braces.
```javascript
const result = 2 + (user.age ?? 18);
```