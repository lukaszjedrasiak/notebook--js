## Basic usage

```html
<div>Hello World!</div> 
```

```javascript
const div = document.querySelector("div");
console.log(div.textContent); // "Hello World!"
```

`document.querySelector()` returns either an `object` or `null`. It depends on whether the item was found in the DOM or not.

## Fallback
```javascript
console.log(div?.textContent);
```
