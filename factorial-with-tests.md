## index.js

```js
const Calculate = {
  factorial(input) {
    if (input < 0) {
      return -1;
    } else if (input === 0) {
      return 1;
    } else {
      return (input * this.factorial(input - 1));
    }
  }
}

module.exports = Calculate;
```

## index_test.js

```js
var assert = require("assert");
var Calculate =  require('../index.js')

describe('Calculate', () => {
  describe('.factorial', () => {
    it('5! equals 120', () => {
      const calculated = Calculate.factorial(5);
      const expected = 120;
      assert.equal(expected, calculated);
    })

    it('3! equals 6', () => {
      const calculated = Calculate.factorial(3);
      const expected = 6;
      assert.equal(expected, calculated);
    })

    it('0! equals 1', () => {
      const calculated = Calculate.factorial(0);
      const expected = 1;
      assert.equal(expected, calculated);
    })

    it('factorial of negative input equals -1', () => {
      const calculated = Calculate.factorial(-10);
      const expected = -1;
      assert.equal(expected, calculated);
    })
  });
});
```