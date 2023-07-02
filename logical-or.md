Returns first true value in the chain

```js
let max = maxWidth || preferences.maxWidth || 500
```

It points to the first true value in chain. Unfortunately 0 is also false, so in this case the better choice will be `??` operator [nullish coalescing operator](nullish-coalescing.md).