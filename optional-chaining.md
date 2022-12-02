basic syntax
```javascript
let name = undefined;
if (user.details && user.details.name && user.details.name.firstName) {
    name = user.details.name.firstName;
}
```

sugar syntax
```javascript
const name = user.details?.name?.firstName;
```

You **cannot** use optional chaining on an object that may not exist. The object **has** to exist. Optional chaining is only used to access a property that may or may not exist.

Optional chaining can be used for arrays. The syntax is `?.[index]`
Optional chaining can be used for functions. The syntax is `functionName?.()`
Optional chaining **cannot** be used for assignment. It's _only_ used for **reading**