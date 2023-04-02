## multiplication table

```js
let table = new Array(10); // 10 rows

for (let i = 1; i < table.length; i++) {
	table[i] = new Array(10); // 10 columns
}

for (let row = 1; row < table.length; row++) {
	for (let col = 0; col < table[row].length; col++) {
		table[row][col] = row * col;
	}
}

table[5][7] // => 35
```