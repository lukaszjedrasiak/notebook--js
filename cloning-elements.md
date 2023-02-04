## basic syntax
```js
element.cloneNode([true][false]);
```

Modes:
- `element.cloneNode(true)` - creates a clone with all attributes and subelements
- `element.cloneNode(false)` - creates a clone without child elements

## examples
```js
let div2 = div.cloneNode(true); // clone the message
div2.querySelector('strong').innerHTML = 'Bye there!'; // change the clone
div.after(div2); // show the clone after the existing div
```