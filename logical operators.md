## II (OR)

```js
true || true // true
false || true // true
true || false // true
false || false // false
```

A chain of OR || returns the first truthy value or the last one if no truthy value is found. If an operand is not a boolean, it’s converted to a boolean for the evaluation.

```js
result = value1 || value2 || value3;
```

## && (AND)

```js
true && true // true
false && true // false
true && false // false
false && false // false
```

## ! (NOT)

```js
!true // false
!0 // true
```

A double NOT `!!` is sometimes used for converting a value to boolean type:

```js
!!"non-empty string" // true
!!null // false
```