## Syntax
```js
element.insertAdjacentHTML(position, htmlString)
```

Available positions:
1. `beforeend` – append: at the end of the element
2. `afterbegin` – prepend: at the beginning of the element

It is recommended to use backsticks in `htmlString`:
- it supports multiline strings (quotes marks doesn't)
- it supports interpolation