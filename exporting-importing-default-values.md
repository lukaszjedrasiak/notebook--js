## exporting

So far, the examples shown have used the named export syntax, in which a module’s resources are exported individually by name. Every module also has the option to export a single value to represent the entire module called the _default export_. Often, though not always, the default export value is an object containing the entire set of functions and/or data values of a module.

The syntax for exporting a default object looks like this:

```js
const resources = {
	valueA,
	valueB
}

export {
	resources as default
};
```

With this syntax, the object containing the module’s resources is first declared and then is exported on the next line. At first glance, it looks like the `resources` object is being exported as a named export. However, the clause `as default` renames the exported object to `default`, a reserved identifier that can only be given to a single exported value.

You may also see this shorthand syntax where the value follows `export default` is the default value to be exported:

```js
const resources = {
	valueA,
	valueB
}

export default resources;
```

## importing

The syntax for importing default exports looks like this:

```js
import importedResources from 'module.js';
```

Notice that the curly braces are gone from the import statement. This syntax is actually shorthand for `import { default as importedResources } from 'module.js` and the imported `default` value may be given any name the programmer chooses.

It should be noted that if the `default` export is an object, the values inside cannot be extracted until after the object is imported, like so:

```js
// This will work...
import resources from 'module.js'const { valueA, valueB } = resources;
// This will not work...
import { valueA, valueB } from 'module.js'
```

Let’s return to the prior example. The **dom-functions.js** module from above could be rewritten to use default exports like so:

```js
/* dom-functions.js */
const toggleHiddenElement = (domElement) => {
	if (domElement.style.display === 'none') {
		domElement.style.display = 'block';
	} else {
		domElement.style.display = 'none';
	}}

const changeToFunkyColor = (domElement) => {
	const r = Math.random() * 255;
	const g = Math.random() * 255;
	const b = Math.random() * 255;
	
	domElement.style.background = `rgb(${r}, ${g}, ${b})`;
}

const resources = {
	toggleHiddenElement,
	changeToFunkyColor
}

export default resources;
```

This default exports object can now be used within **secret-messages.js** like so:

```js
import domFunctions from '../modules/dom-functions.js';

const { toggleHiddenElement, changeToFunkyColor } = domFunctions;
const buttonElement = document.getElementById('secret-button')
const pElement = document.getElementById('secret-p');

buttonElement.addEventListener('click', () => {
	toggleHiddenElement(pElement);  changeToFunkyColor(buttonElement);
});
```

Notice how `toggleHiddenElement()` and `changeToFunkyColor()` are now methods of the imported object called `domFunctions` and are extracted using [ES6 destructuring syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)! It should be noted that the identifier `domFunctions` can be chosen as the programmer sees fit. If you recall, the syntax used in the snippet above is shorthand for:

```js
import { default as domFunctions } from '../modules/dom-functions.js';
```