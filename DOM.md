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

## DOM nodes classes
![dom-class-hierarchy](dom-class-hierarchy.svg)

The classes are:
- **EventTarget** – is the root “abstract” class for everything. Objects of that class are never created. It serves as a base, so that all DOM nodes support so-called “events”, we’ll study them later.
- **Node** – is also an “abstract” class, serving as a base for DOM nodes. It provides the core tree functionality: `parentNode`, `nextSibling`, `childNodes` and so on (they are getters). Objects of `Node` class are never created. But there are other classes that inherit from it (and so inherit the `Node` functionality)
- **Document** – for historical reasons often inherited by `HTMLDocument` (though the latest spec doesn’t dictate it) – is a document as a whole. The `document` global object belongs exactly to this class. It serves as an entry point to the DOM.
- **CharacterData** – an “abstract” class, inherited by:
	- **Text** – the class corresponding to a text inside elements, e.g. `Hello` in `<p>Hello</p>`.
	- **Comment** – the class for comments. They are not shown, but each comment becomes a member of DOM.
- **Element** – is the base class for DOM elements. It provides element-level navigation like `nextElementSibling`, `children` and searching methods like `getElementsByTagName`, `querySelector`. A browser supports not only HTML, but also XML and SVG. So the `Element` class serves as a base for more specific classes: `SVGElement`, `XMLElement` (we don’t need them here) and `HTMLElement`.
- **HTMLElement** is the basic class for all HTML elements. We’ll work with it most of the time. It is inherited by concrete HTML elements:
	- **HTMLInputElement** – the class for `<input>` elements,
	- **HTMLBodyElement** – the class for `<body>` elements,
	- **HTMLAnchorElement** – the class for `<a>` elements,

> DOM nodes are regular JavaScript objects. They use prototype-based classes for inheritance.

## DOM nodes properties
- `nodeType` - numeric value: `1` for elements,`3` for text nodes, and a few others for other node types. Read-only.
- `nodeName` - for every node
- `tagName` - only for Element nodes
- `innerHTML` - allows to get the HTML inside the element as a string. Valid only for element nodes.
- `outerHTML` - it contains `innerHTML` + the element itself
- `nodeValue` / `data` - similar to `innerHTML` but valid for text nodes or comments
- `textContent` - similar to `innerHTML` but contains only plain text without tags
- `hidden` - technically works the same as `display: none` in css
- `value` - value of `<input>`, `<select>` and `<textarea>`
- `href` - `href` from `<a href='...'>`
- `id` - value of `id` attribute

The full list of properties available for given elements can be fetched from:
- https://html.spec.whatwg.org/#htmlinputelement
- output of `console.dir(element)`
- list of 'DOM properties' in devtools

## methods
[searching and selecting elements](searching-and-selecting-elements.md)
[creating elements](creating-elements)
[changing elements](changing-elements.md)
[sizing elements](sizing-elements)
[cloning elements](cloning-elements)
[removing elements](removing-elements)

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
