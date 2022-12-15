## selecting a single item

```javascript
document.querySelector("your-CSS-selector-here");
```

If there are multiple items that satisfy the CSS selector that you specified, only the first one is returned. Later on, we'll see how you can select more than 1 item at a time.

Type of selectors:
1. Type: `"h1"`
2. ID: `"navbar"`
3. Class: `".item"`
4. Descendant selector: `"#banner .item"`
5. Attribute: `"[disabled]"`

`document.querySelector("CSS-selector")` returns an **object** which is an instance of `HTMLElement`. HTMLElement is the parent class that every single HTML element in your page inherits from. This means that every element on your page is an instance of a single class which is `HTMLElement`.

### alternative methods
```javascript
const navbar = document.getElementById("navbar"); // you should skip the #
```

## selecting multiple elements
```js
document.querySelectorAll("your-CSS-selector-here");
```

While `document.querySelector()` might return `null` (when no items are found), the `document.querySelectorAll()` will **always** return a [[NodeList]] - of 0 or all DOM elements. This is an important difference.

A **NodeList** is a collection of DOM elements. This means that it is a variable that contains several DOM elements.


