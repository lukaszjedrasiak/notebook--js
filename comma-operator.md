The comma operator allows us to evaluate several expressions, dividing them with a comma `,`. Each of them is evaluated but only the result of the last one is returned.

For example:
```js
let a = (1 + 2, 3 + 4);
console.log(a); // 7 (the result of 3 + 4)`
```

Here, the first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.

## usage

```js
for (let i=0,j=10; i < j; i++,j--) {
	console.log(i+j);
}
```