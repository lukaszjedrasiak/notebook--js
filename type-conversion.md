## explicit conversion

### methods

- `String(value)` – into string
- `Number(value)` – into number
- `Boolean(value)` – into boolean. Values that are intuitively “empty”, like 0, an empty string, null, undefined, and NaN, become false. Other values become true.
- [parseInt()](parseInt)
- `parseFloat()`

> [!warning]
> `Number(undefined) // Nan`
> `Boolean("0") // true`
> `Boolean(" ") // true`

### shorthands

- `x + ""` – String(x)
- `+x` – Number(x)
- `x-0` – Number(x)
- `!!x` – Boolean(x)

```js
let apples = "2";
let oranges = "3";
console.log(apples + oranges); // "23"
console.log(+apples + +oranges); // 5
```

## implicit conversion

### comparisons

`==` operator convert data types.
`===` do not convert data types.