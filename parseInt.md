## syntax

```javascript
Number.parseInt(string, radix);
```

Radix: The `radix` is the base of the numerical system that you'd like to use. For most use cases the radix you'd like to use is `10` which represents the way we count numbers in our everyday lives.

## examples

```js
parseInt("11", 2) // => 3 (1*2+1)
parseInt("ff", 16) // => 255 (15*16+15)
parseInt("077", 8) // => 63 (7*8+7)
parseInt("077", 10) // => 10
```

## usage

This method is better than `+` or `Number()` notation, because it can ommit chars (i.e. units) in string. 

```js
alert( parseInt('100px') ); // 100
alert( parseFloat('12.5em') ); // 12.5
alert( parseInt('12.3') ); // 12, only the integer part is returned
alert( parseFloat('12.3.4') ); // 12.3, the second point stops the reading
```

[Mathematical bases](https://simple.wikipedia.org/wiki/Base_(mathematics))
