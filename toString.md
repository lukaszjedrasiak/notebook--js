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