## breaking the loop

```js
let sum = 0;
while (true) {
  let value = +prompt("Enter a number", '');
  if (!value) break; // (*)
  sum += value;
}
alert( 'Sum: ' + sum );
```

## continue to the next iteration

```js
for (let i = 0; i < 10; i++) {

  // if true, skip the remaining part of the body
  if (i % 2 == 0) continue;

  alert(i); // 1, then 3, 5, 7, 9
}
```

Effects of `continue` depends on the loop type:
- `while` – interpreter goes to the condition at the beginning. If is true the loop starts again.
- `do/while` – interpreter goes to the condition at the end.
- `for` – iterator is updated and then interpreter checks the condition
- `for/of` & `for/in` – interpreter goes to the next element.

## labels for break/continue

In nested loops, the `break` command will terminate only the inside loop. If we need to terminate all two loops (the parent and the child) we may use the label for the parent loop and then use the same label with the break command:

```js
outer: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    let input = prompt(`Value at coords (${i},${j})`, '');
    // if an empty string or canceled, then break out of both loops
    if (!input) break outer; // (*)
    // do something with the value...
  }
}
alert('Done!');
```