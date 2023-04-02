## selecting a single item

```javascript
document.querySelector("your-CSS-selector-here");
```

This method is an equivalent of this one, described later:
```js
document.querySelectorAll("your-CSS-selector-here")[0]
```

If there are multiple items that satisfy the CSS selector that you specified, **only the first one is returned**.

Type of selectors:
1. Type: `"h1"`
2. ID: `"#navbar"`
3. Class: `".item"`
4. Descendant selector: `"#banner .item"`
5. Attribute: `"[disabled]"`

`document.querySelector("CSS-selector")` returns an **object** which is an instance of `HTMLElement`. HTMLElement is the parent class that every single HTML element in your page inherits from. This means that every element on your page is an instance of a single class which is `HTMLElement`.

### alternative methods

```javascript
const navbar = document.getElementById("navbar"); // you should skip the #
```

Remember:
- `id` must be unique along the document. Otherwise, this method may return any of found elements at random
- this method may be called only on `document` object.

Similar methods:
- `getElementsByTagName(tag)` - returns the collection. The `tag` parameter can be also a star `*` for any tags.
- `getElementsByClassName(className)`
- `getElementsByName(name)`

These methods return an array of elements, instead of just one element. You can use bracket notation to access individual elements of an array.

```js
const el = document.getElementsByClassName(class)[0];
```

## selecting multiple elements
```js
document.querySelectorAll("your-CSS-selector-here");
```

While `document.querySelector()` might return `null` (when no items are found), the `document.querySelectorAll()` will **always** return a [[NodeList]] - of 0 or all DOM elements. This is an important difference.

A **NodeList** is a collection of DOM elements. This means that it is a variable that contains several DOM elements.


