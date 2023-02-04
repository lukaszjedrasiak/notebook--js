## definition
The DOM (Document Object Model) is a JavaScript object & API (a set of functions) that represents the HTML of your page. It lets you interact from JavaScript with the elements on your page. You can read and change text, add and delete items, and a lot more.

In other words: an HTML/XML document is represented inside the browser as the DOM tree.

There are 12 node types. In practice we usually work with 4 of them:
1.  **document** – the “entry point” into DOM.
2.  **element nodes** – HTML-tags, the tree building blocks.
3.  **text nodes** – contain text.
4.  **comments** – sometimes we can put information there, it won’t be shown, but JS can read it from the DOM.

> We usually want to manipulate only **element nodes** - the nodes that represent tags and form the structure of the page.

## basic elements
| tag  | element | node |
| ---- | --- | ---  |
| html | HTMLHtmlElement | document.documentElement |
| body | HTMLBodyElement | document.body |
| head | HTMLHeadElement | document.head |

> If script is inside `head` then calling `document.body` may cause `null` result (it hasn't been loaded yet)

## methods
[searching and selecting elements](searching-and-selecting-elements.md)
[changing elements](changing-elements.md)

### matches
This method doesn't search anything. It checks if given element matches the given css selector and returns true or false respectively.
```js
if(element.matches('css-selector')) {
	// do sth
}
```

### closest
This method looks for the nearest ancestor of given element that matches the given css selector. In other words, the method `closest` goes up from the element and checks each of parents. If it matches the selector, then the search stops, and the ancestor is returned.

### contains
This method returns true if `elementB` is inside `elementA` or when `elementA == elementB`
```js
elementA.contains(elementB)
```

## others
[DOM collections](dom-collections)
[events](events)