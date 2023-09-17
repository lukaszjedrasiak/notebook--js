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

**short circuit** – if the value on the left side of `?` sign is `null` or `undefined` the whole expression is `undefined` without checking the right side of it.


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