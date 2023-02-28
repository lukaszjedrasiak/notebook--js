files structure

```
secret-image/  
|-- secret-image.html  
|-- secret-image.js  
secret-messages/  
|-- secret-messages.html  
|-- secret-messages.js  
modules/  
|-- dom-functions.js
```

exported modules

```js
/* dom-functions.js */  
const toggleHiddenElement = (domElement) => {  
    if (domElement.style.display === 'none') {  
      domElement.style.display = 'block';  
    } else {  
      domElement.style.display = 'none';  
    }  
}  
  
const changeToFunkyColor = (domElement) => {  
  const r = Math.random() * 255;  
  const g = Math.random() * 255;  
  const b = Math.random() * 255;  
  
  domElement.style.background = `rgb(${r}, ${g}, ${b})`;  
}  
  
export { toggleHiddenElement, changeToFunkyColor };
```

target files

```js
/* secret-messages.js */  
import { toggleHiddenElement, changeToFunkyColor } from '../modules/dom-functions.js';  
  
const buttonElement = document.getElementById('secret-button');  
const pElement = document.getElementById('secret-p');  
  
buttonElement.addEventListener('click', () => {  
  toggleHiddenElement(pElement);  
  changeToFunkyColor(buttonElement);  
});
```

html file

```html
<!-- secret-messages.html -->  
<html>  
  <head>  
    <title>Secret Messages</title>  
  </head>  
  <body>  
    <button id="secret-button"> Press me... if you dare </button>  
    <p id="secret-p" style="display: none"> Modules are fancy! </p>  
    <script type="module" src="./secret-messages.js"> </script>  
  </body>  
</html>
```