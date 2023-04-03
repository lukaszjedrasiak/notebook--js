Set is collection of values similar to Arrays. But unlike the arrays:
- values are not stored in order,
- values do not have indexes,
- values can not repeat (duplicates are not allowed).

## syntax

```js
let s = new Set() // empty set
let t = new Set([1, s]) // new set with two elements
```

The argument of Set class can be any iterable object.

```js
let unique = new Set('Mississippi') // => {'M', 'i', 's', 'p'}
```

## methods and properties

```js
let s = new Set();
s.size;
s.add(el);
s.delete(el);
s.clear();
```

The most common methods is checking if the given element is inside the set.

```js
let oneDigitPrimes = new Set([2, 3, 5, 7]);
oneDigitPrimes.has(2) // => true
oneDigitPrimes.has(4) // => false
oneDigitPrimes.has("5") // => false
```

Sets are iterable.

```js
let oneDigitPrimes = new Set([2, 3, 5, 7]);
let sum = 0;
for (let p of oneDigitPrimes) {
	sum += p;
}
sum // => 17
```

Sets can be converted to an array.

```js
let oneDigitPrimes = new Set([2, 3, 5, 7]);
let PrimesArray = [...oneDigitPrimes];
PrimesArray; // => [2, 3, 5, 7]
```

Sets can be used with `forEach()` method.

```js
let oneDigitPrimes = new Set([2, 3, 5, 7]);
let product = 1;
oneDigitPrimes.forEach(n => product *= n);
product // => 210
```