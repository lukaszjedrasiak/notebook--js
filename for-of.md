## example
```javascript
const people = ["Sam", "Alex"];

for (const person of people) {
    console.log(person);
}
```

## benefits
1.  The Syntax (it all comes down to your personal preference if you prefer this over `.forEach()`)
2.  Being able to use the `break` and `continue` keywords.

## usage
The for...of works not only on arrays but on all data types and variables that are "iterable". Iterable means data types that you can iterate over. The list includes:
- Strings,
- Arrays,
- NodeList (the result of document.querySelectorAll),
- Map,
- Set.

Example:
```js
let data = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let sum = 0;

for (let element of data) {
	sum += element;
}

console.log(sum);
```

### usage with objects

Objects are not iterable by default. If you want to iterate over object you should use:
- [for/in](for-in) loop,
- for/of loop with `Object.keys()`,
- for/of loop with `Object.values()`,
- for/of loop with `Object.entries()`.

```js
//Object.keys()

let o = {
	x: 1,
	y: 2,
	z: 3
}

let keys = "";
for (let k of Object.keys(o)) {
	keys += k;
}

keys // => "xyz"
```

```js
//Object.values()

let o = {
	x: 1,
	y: 2,
	z: 3
}

let sum = 0;
for (let v of Object.values(o)) {
	sum += v;
}

sum // => 6
```

```js
//Object.entries()

let o = {
	x: 1,
	y: 2,
	z: 3
}

let pairs = "";
for (let [k, v] of Object.entries(o)) {
	pairs += k + v;
}

pairs // => "x1y2z3"
```

### usage with strings

```js

let frequency = {};

for (let letter of 'mississippi') {
	if (frequency[letter]) {
		frequency[letter]++;
	} else {
		frequency[letter] = 1;
	}
}

console.table(frequency);
```