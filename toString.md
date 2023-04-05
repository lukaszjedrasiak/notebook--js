## Syntax

```js
n.toString([base])
```

Base can be:
- binary
- octal
- hexadecimal
- decimal (default)

```js
let n = 17
let binary = "0b" + n.toString(2) // => 0b10001
let octal = "0o" + n.toString(8) // => 0o21
let hex = "0x" + n.toString(16) // => 0x11
```

The `base` can vary from `2` to `36`. By default it’s `10`.

Common use cases for this are:
- **base=16** is used for hex colors, character encodings etc, digits can be `0..9` or `A..F`.
- **base=2** is mostly for debugging bitwise operations, digits can be `0` or `1`.
- **base=36** is the maximum, digits can be `0..9` or `A..Z`. The whole latin alphabet is used to represent a number. A funny, but useful case for `36` is when we need to turn a long numeric identifier into something shorter, for example to make a short url. Can simply represent it in the numeral system with base `36`:

```js
console.log((123456).toString(36)); // 2n9c
```