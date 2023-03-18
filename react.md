[jsx conditionals](jsx-conditionals)

## importing

```js
import React from 'react';

import ReactDOM from 'react-dom';
```

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