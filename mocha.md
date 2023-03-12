## source
https://mochajs.org/

## installing

```bash
npm init
```

```bash
npm install mocha -D
```

Add a script to `package.json`
```json
"scripts": {  
  "test": "mocha"  
}
```

This connects the command line command `npm test` with the Mocha package. Now you can call Mocha with the following command:
```bash
npm test
```

## tests phases
- _Setup_ - create objects, variables, and set conditions that your test depends on  
- _Exercise_ - execute the functionality you are testing
- _Verify_ - check your expectations against the result of the exercise phase. You can use the `assert` library here
- _Terdown_ - we often add a _teardown_ step to the end of our tests. The teardown phase makes our tests _isolated_ by resetting the environment before the next test runs.

### example
```js
const assert = require('assert');

// Naive approach

describe('.pop', () => {
  it('returns the last element in the array [naive]', () => {
    assert.ok(pop(['padawan', 'knight']) === 'knight'); 
  });
});

// 3 phase approach
describe('.pop', () => {
  it('returns the last element in the array [3phase]', () => {
    // Setup
    const knightString = 'knight';
    const jediPath = ['padawan', knightString];

    // Exercise
    const popped = pop(jediPath);

    // Verify
    assert.ok(popped === knightString);

	// Teardown
	// clean envirnoment in this phase
  });
});
```

## hooks

Hooks are functions which are common for many tests. They are often used in setup and teardown phase.

These functions are:
- `beforeEach(callback)` - `callback` is run before each test
- `afterEach(callback)` - `callback` is run after each test
- `before(callback)` - `callback` is run before the first test
- `after(callback)` - `callback` is run after the last test

### example

```js
describe('messing around with hooks', () => {  
  
  let testValue; // Variable used by both tests  
  
  beforeEach(() => {  
    testValue = 5;  
  });  
  
  it('should add', () => {  
    // testValue = 5 <-- moved to beforeEach()  
    testValue = testValue + 5;  
    assert.equal(testValue, 10);  
  });  
  
  it('should multiply', () => {  
    // testValue = 5 <-- moved to beforeEach()  
    testValue = testValue * 5;  
    assert.equal(testValue, 25);  
  });  
  
});
```