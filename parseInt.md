Sample usage
```javascript
Number.parseInt(string, radix);
```

Radix: The `radix` is the base of the numerical system that you'd like to use. For most use cases the radix you'd like to use is `10` which represents the way we count numbers in our everyday lives.

Examples:
```js
parseInt("11", 2) // => 3 (1*2+1)
parseInt("ff", 16) // => 255 (15*16+15)
parseInt("077", 8) // => 63 (7*8+7)
parseInt("077", 10) // => 10
```

[Mathematical bases](https://simple.wikipedia.org/wiki/Base_(mathematics))
