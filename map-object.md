Map is collection of pairs `key -- value`.

Map is created from an array, which each element is another array that consists two elements: key and assigned value.

## example

```js
let m = new Map(); // empty map
let n = new Map([
	["one", 1],
	["two", 2]
]);
```

## methods

```js
n.get("one") // => 1
n.set("three", 3); // => Map(3) {'one' => 1, 'two' => 2, 'three' => 3}
n.has("three") // => true
n.delete("three")
```

Maps are iterable.
```js
let m = new Map([
	["one", 1],
	["two", 2],
	["three", 3]
]);

[...m];

for (let [key, value] of m) {
	console.log(key, value);
}
```

Other ways of destructuring.
```js
[...m.keys()] // => ['one', 'two', 'three']
[...m.values()] // => [1, 2, 3]
[...m.entries()] // => equivalent of [...m]
```

forEach method:
```js
m.forEach((value, key) => console.log(key + ": " + value));
```

Notice that this method looks similar as in array – the first argument is value, and the second is key.