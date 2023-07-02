> ** TO DO **
> learn more about optional chaining in iterations via arrays
> i.e.: `data.documents?.forEach(item => ...`

**The nullish coalescing operator `??` provides a short way to choose the first “defined” value from a list, instead of displaying "null" or "undefined".**

## example

```js
let len = book.author.surname
```

## explicit declaration

```js
let surname = undefined;
if (book) {
	if (book.author) {
		surname = book.author.surname
	}
}
```

## sugar syntax

```js
surname = book && book.author && book.author.surname;
```

```js
let surname = book?.author?.surname;
```

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

We can rewrite result = a ?? b using the operators that we already know, like this:
```js
result = (a !== null && a !== undefined) ? a : b;
```