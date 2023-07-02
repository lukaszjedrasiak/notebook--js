Used for numbers of any kind: integer or floating-point, integers are limited by $±(2^{53}-1)$.

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

---

A number is stored in memory in its binary form, a sequence of bits – ones and zeroes. But fractions like `0.1`, `0.2` that look simple in the decimal numeric system are actually unending fractions in their binary form.

What is `0.1`? It is one divided by ten `1/10`, one-tenth. In decimal numeral system such numbers are easily representable. Compare it to one-third: `1/3`. It becomes an endless fraction `0.33333(3)`.

So, division by powers `10` is guaranteed to work well in the decimal system, but division by `3` is not. For the same reason, in the binary numeral system, the division by powers of `2` is guaranteed to work, but `1/10` becomes an endless binary fraction.

There’s just no way to store _exactly 0.1_ or _exactly 0.2_ using the binary system, just like there is no way to store one-third as a decimal fraction.

The numeric format IEEE-754 solves this by rounding to the nearest possible number. These rounding rules normally don’t allow us to see that “tiny precision loss”, but it exists.

---

## writing numbers

```js
let nmb = 10000000000 // standard
let nmb = 1_000_000_000 // syntactic sugar
let nmb = 1e9 // 

let mcs = 0.000001
let mcs = 1e-6
```

## special numeric values
- `Infinity`
- `-Infinity`

```js
alert( isFinite("15") ); // true
alert( isFinite("str") ); // false, because a special value: NaN
alert( isFinite(Infinity) ); // false, because a special value: Infinity
```

- `NaN` - this value is not equal to any other value - even other `NaN`! If you want to check if a variable is `NaN` you should use a global function `isNaN()`

```js
alert( isNaN(NaN) ); // true
alert( isNaN("str") ); // true

alert( NaN === NaN ); // false
```

> methods `isFinite()` and `isNan()` are NOT the same as `Number.isFinite()` and `Number.isNaN()` :)