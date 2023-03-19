[jsx conditionals](jsx-conditionals)
[components](components)

## importing

```js
import React from 'react';
```

This creates an object named `React` which contains methods necessary to use the React library.

```js
import ReactDOM from 'react-dom';
```

The methods imported from `'react-dom'` are meant for interacting with the DOM.

The DOM is _used_ in React applications, but it isn’t _part_ of React. After all, the DOM is also used in countless non-React applications. Methods imported from `'react'` are only for pure React purposes, such as creating components or writing JSX elements.

## jsx

JSX expressions:
```js
const header = (
	<h1>heading here</h1>
);
```

## reactDOM

### render

Basic syntax
```js
ReactDOM.render(jsxExpression, htmlElement)
```

Example
```js
ReactDOM.render(  
  <h1>2 + 3</h1>,  
  document.getElementById('app')  
);
```

### self-closing tags

You have to use `/` in self-closing tags

```js
<br/>
<img/>
```

## js in jsx in js

This code will render '2+3' literally.
```js
ReactDOM.render(  
  <h1>2 + 3</h1>,  
  document.getElementById('app')  
);
```

This code will render '5', because expression inside curly braces are treated as JS syntax.
```js
ReactDOM.render(
	<h1>{2+3}</h1>,
	document.getElementById('app');
)
```

### variables in jsx

```js
const sampleVariable = 'text';

ReactDOM.render(<p>{sampleVariable}</p>, document.getElementById('app'));
```

```js
const goose = 'https://example.com/img.jpg';

const gooseImg = (
  <img 
    src={goose}
  />
)
```

### events listeners

An event listener attribute’s _value_ should be a function. The above example would only work if `myFunc` were a valid function that had been defined elsewhere:

```js
function myFunc() {  alert('Make myFunc the pFunc... omg that was horrible i am so sorry');} 

<img onClick={myFunc} />
```

## .map in jsx

```js
const strings = ['Home', 'Shop', 'About Me'];  
  
const listItems = strings.map((string, i) => <li>{string}</li>);  
  
<ul key={'no_' + i}>{listItems}</ul>
```