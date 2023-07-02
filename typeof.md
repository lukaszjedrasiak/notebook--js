The `typeof` operator checks the value to its right and _returns_, or passes back, a string of the data type.

```js
console.log(typeof newVariable);
```

Allowed syntax:

```js
typeof(variable);
```

## returned values

|          x          |  typeof x   |
| ------------------- | ----------- |
| undefined           | "undefined" |
| null                | "object"    |
| true / false        | "boolean"   |
| number / NaN        | "number"    |
| bigint number       | "bigint"    |
| string              | "string"    |
| symbol              | "symbol"    |
| function            | "function"  |
| non-function object | "object"    |