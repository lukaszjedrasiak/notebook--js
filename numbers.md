Used for numbers of any kind: integer or floating-point, integers are limited by `±(253-1)`.

You can also use:
- hexadecimal numbers: `0xff`,
- octal numbers: `0o377`,
- binary numbers: `0b10101`

See also: properties and methods of [Number](Number) object.
See also: methods of [Math](Math object).

Numbers in JS are not precise. If need to express a currency you should use the smallest unit, i.e. cents instead of dollars.

```js
let x = 0.3 - 0.2
let y = 0.2 - 0.1
x === y // false
x === 0.1 // false
y === 0.1 // true
```

## special numeric values
- `Infinity`
- `-Infinity`
- `NaN` - this value is not equal to any other value - even other `NaN`! If you want to check if a variable is `NaN` you should use a global function `isNaN()`