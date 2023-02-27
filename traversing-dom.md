1. `element.parentElement` - property that returns the parent element of the current element.
2. `element.parentNode` - returns the parent of the specified element in the DOM hierarchy. Note that the `document` element is the _root node_ so its `.parentNode` property will return `null`. 
3. `element.children` - The `.children` property returns an array of the specified element’s children. If the element does not have any children, it will return `null`.
4. `element.closest("CSS-selector")` method returns the **closest parent** that matches the `CSS-selector`.