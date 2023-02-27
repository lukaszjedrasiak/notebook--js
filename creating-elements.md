## creating
Example:
```javascript
const paragraph = document.createElement("p");
paragraph.id = 'sampleId' //add ID to the paragraph
paragraph.classList.add("text-center");
paragraph.textContent = "Hello World";
console.log(paragraph); // <p class="text-center">Hello World</p> (as an element not as a string)
```

## inserting into DOM
Insertion methods:
-   `node.append(...nodes or strings)` – append nodes or strings _at the end_ of `node`,
-   `node.prepend(...nodes or strings)` – insert nodes or strings _at the beginning_ of `node`,
-   `node.before(...nodes or strings)` –- insert nodes or strings _before_ `node`,
-   `node.after(...nodes or strings)` –- insert nodes or strings _after_ `node`,
-   `node.replaceWith(...nodes or strings)` –- replaces `node` with the given nodes or strings.

> If we use this method to insert a HTML string, the text is inserted “as text”, not “as HTML”, with proper escaping of characters such as `<`, `>`. I.e. string `<p>Hello</p>` will be inserted as `&lt;p&gt;Hello&lt;/p&gt;`

## legacy inserting
- `parentElement.appendChild(element)` – insert as the last child of `parentElement`
- `parentElement.insertBefore(element, nextSibling)` – inserts `element` before `nextSibling` into `parentElement`
- `parentElement.replaceChild(element, oldChild)` – replaces `oldChild` with `element` among children of `parentElement`
- `parentElement.removeChild(element)` – removes `element` from `parentElement`

## insertAdjacentHTML
Method used to insert a string, but as a HTML object.

```js
element.insertAdjacentHTML(position, htmlString)
```

Available positions:
1. `beforebegin` – insert before the element
2.  `afterbegin` – insert at the beginning of the element (prepend)
3. `beforeend` – insert at the end of the element (append)
4. `afterend` – insert after the element

It is recommended to use backsticks in `htmlString`:
- it supports multiline strings (quotes marks doesn't)
- it supports interpolation

## documentFragment
`DocumentFragment` is a special DOM node that serves as a wrapper to pass around lists of nodes. We can append other nodes to it, but when we insert it somewhere, then its content is inserted instead.

```js
function getListContent() {
	let fragment = new DocumentFragment();
	for(let i=1; i<=3; i++) {
		let li = document.createElement('li');
		li.append(i);
		fragment.append(li);
	}
	return fragment;
}

ul.append(getListContent()); // (*)
```