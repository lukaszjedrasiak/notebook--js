DOM collections are `nodeList` - see more in 'searching and selecting' method.

## vocabulary
1. ancestors - parent, the parent of parent, its parent and so on. The ancestors together form the chain of parents from the element to the top
2. children (child nodes) - direct children of element
3. descendants - all nested elements of parent element
4. siblings - nodes that are children of the same parent

## list
- `childNodes` - list of all child nodes
- ``...``

## collections methods
- `hasChildNodes`
- `...`

## collections properties
These match all nodes types (also comments, text, etc.)
- `firstChild`
- `lastChild`
- `nextSibling`
- `previousSibling`
- `parentNode`

These match only element nodes:
- `children`
- `firstElementChild`
- `lastElementChild`
- `previousElementSibling`
- `nextElementSibling`
- `parentElement`

See also: [table collection properties](table-collection-properties)

> The `parentElement` property returns the “element” parent, while `parentNode` returns “any node” parent. These properties are usually the same: they both get the parent.
> 
> With the one exception of `document.documentElement`. The root node (`<html>` / `documentElement` / `HTMLHtmlElement`) has `document` as its parent. But `document` is not an element node. So:
> - `document.documentElement.parentNode` returns `document`
> - `document.documentElement.parentElement` returns `null`