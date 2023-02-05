[element.textContent](textContent)
[element.innerHTML](innerHTML)
[element.value](value)

## classes
If we want to add or read single css class on element we can use `className` property. This way replaces the whole string of classes.
```js
console.log(element.className); //
```

List of methods to dynamically add or remove classes **on** element.
1. `element.classList.add()`
2. `element.classList.remove()`
3. `element.classList.contains(className)` -> returns true or false
4. `element.classList.toggle(className)` -> ads or removes a class on element (depends on if it is present or not)
5. `element.classList.replace(oldClassName, newClassName)` -> one line method to remove old class and add new one
6.  `element.classList.add(firstClass, secondClass)` -> ads multiple classes at one time
7. `element.classList.remove(firstClass, secondClass)` -> removes multiple classes at one time

1. You can only access `.classList` on a single element. If you had a NodeList (from `document.querySelectorAll`), then you need to loop through it with forEach.
2. To be able to manage classes (in this case remove a class), you have to start by accessing `.classList`. A common mistake is to try and call ❌`element.remove()` or ❌`element.removeClass()` but these methods **do not exist**.
3. All the methods under `classList` expect a **class name**. So you should **not** prefix the class name with a dot. ❌`element.classList.remove(".highlighted")` would not work as expected here.

### examples

Switching between tabs
```js
export const deactivateAllTabs = () => {
    document.querySelectorAll(".tab").forEach(tab => {
        tab.classList.remove("active");
    });
    // OR, since only one tab can be active at a time: 
    // document.querySelector(".tab.active").classList.remove("active");
}

/**
 * @param {HTMLElement} tab
 */
export const activateClickedTab = tab => {
    tab.classList.add("active");
}

```

Switching between theme
```js
const toggleDarkTheme = () => {
    document.documentElement.classList.toggle('dark');
}
```

## attributes / properties
When the browser loads the page, it “reads” (another word: “parses”) the HTML and generates DOM objects from it. For element nodes, most standard HTML attributes automatically become properties of DOM objects. For instance, if the tag is `<body id="page">`, then the DOM object has `body.id="page"`.

> In short: 
> -   Attributes – is what’s written in HTML.
> -   Properties – is what’s in DOM objects.

### methods for attributes
1. `element.getAttribute(key)` method is used to get the value of a certain attribute by its key.
2. `element.removeAttribute(key)` is used to remove an attribute.
3. `element.setAttribute(key, value)` is used to write a new attribute (or update the value of an old one that already exists).
4. `element.hasAttribute(key)` method is used to check whether an attribute exists or not. The function always returns a boolean.
5. `element.attributes` is a collection of all attributes

### custom attributes
Custom attributes should be prefixed with `data-`, to avoid any future conflict with new attributes in HTML, i.e.:

```html
<form id="one" data-currency="EUR"> ... </form>
```

You can access these custom attributes via `dataset` object:
```js
const element = document.querySelector('#one');
const currency = element.dataset.currency;
```

> Multiword attributes like `data-order-state` become camel-cased: `dataset.orderStat`

Data values are always saved as a string. So if you want to access the boolean value use the following condition: `value === "true"`. It allows you to convert `"true"` and `"false"` into a boolean.

## styles
```js
const element = document.querySelector('selector');
element.style.property = 'value';
```

We do recommend that you update classes instead of styles directly when possible. Changing styles via JS is almost the same as CSS. The only difference is that we've got to use camelCase rather than kebab case.

| **CSS**          | **JS**          |
|------------------|-----------------|
| background-color | backgroundColor |
| color            | color           |
| font-size        | fontSize        |
| z-index          | zIndex          |

We can remove style from element in two ways
- `element.style.property = ''`
- `element.style.removeProperty(propery)`

### reading styles
```js
getComputedStyle(element, [pseudo]) // returns an element with all styles applied.
```

> The values returned by `getComputedStyle` are resolved. It means that computed values (the final ones - result of cascade and inheritance) are converted into fixed and absolute units, like `px`. 

## traversing
1. `element.parentElement` - property that returns the parent element of the current element.
2. `element.closest("CSS-selector")` method returns the **closest parent** that matches the `CSS-selector`.