## documentation
https://nodejs.org/api/assert.html

## including

```js
const assert = require('assert');
```

## methods

### assert.ok

```js
assert.ok(6 - 1 === 5);
```

In this case `6 - 1 === 5` evaluates to `true`, so no error is thrown.

If an argument passed to `assert.ok()` evaluates to `false`, an `AssertionError` is thrown. The error communicates to Mocha that a test has failed, and Mocha logs the error message to the console.

### assert.equal

This method is an equivalent of `==` comparison in `assert.ok` method.

```js
assert.ok(landAnimals[2] == waterAnimals[2]);  
assert.equal(landAnimals[2], waterAnimals[2]);
```

### assert.strictEqual

This method is an equivalent of `===` comparison in `assert.ok` method.

### assert.deepEqual

This method is an equivalent of `==` comparison during comparing values of two objects or arrays.

```js
const objA = {property1: valueA1, property2: valueA2};
const objB = {property1: valueB1, property2: valueB2};

// assert
assert.deepEqual(objA, objB);

// equivalent
objA.property1 == objB.property1;
objA.property2 == objB.property2;
```