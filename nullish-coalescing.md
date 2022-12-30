> ** TO DO **
> learn more about optional chaining in iterations via arrays
> i.e.: `data.documents?.forEach(item => ...`

It allows to assign default value, if the left-hand variable has `null` or `undefined` state.

```javascript
const getName = name => {
    return name ?? "N/A";
}

console.log(getName("Sam")); // "Sam"
console.log(getName(undefined)); // "N/A"
console.log(getName(null)); // "N/A"
```

This operator is useful to avoid showing `undefined` or `null` to the User Interface, which are often signs of bugs.

nullish coalescing with the optional chaining
```javascript
const name = user.details?.name?.firstName ?? "N/A";
```

Nullish coalescing has lower precedence than such operators like `+` or `-`. So you need to wrap the operator with curly braces.
```javascript
const result = 2 + (user.age ?? 18);
```

