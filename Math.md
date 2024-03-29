## .random

```js
Math.random() // returns a random number between 0 (inclusive) and 1 (exclusive).
```

```js
Math.random() * 100 // returns a random number between 0 and 100
```

### example

```js
const rollTheDice = () => {

  // Math.random() gives us a random number from 0 up to, but not including, 1

  // We multiplied that by 6 to get a number between 0 and up to, but not including, 6
  // But since we actually wanted numbers from 1 to 6, inclusive, we added 1

    let die1 = Math.floor(Math.random() * 6 + 1);
    let die2 = Math.floor(Math.random() * 6 + 1);
    return die1 + die2
}
```

## rounding methods

| Number | Math.floor | Math.ceil | Math.round | Math.trunc |
| ------ | ---------- | --------- | ---------- | ---------- |
|    3.1 |          3 |         4 |          3 |          3 |
|    3.6 |          3 |         4 |          4 |          3 |
|   -1.1 |         -2 |        -1 |         -1 |         -1 |
|   -1.6 |         -2 |        -1 |         -2 |         -1 |

### .floor
**Rounds down** and returns the largest integer less than or equal to a given number.
```js
Math.floor() // takes a decimal number, and rounds down to the nearest whole number
```

### .ceil
**Rounds up** and returns the smaller integer greater than or equal to a given number.
```js
Math.ceil()
```

## other
- `Math.max(a, b, c)` – returns the greatest value
- `Math.min(a, b, c)` – returns the smalles value
- `Math.pow(n, power)` – returns `n` raised to given power