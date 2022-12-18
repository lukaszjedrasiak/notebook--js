`innerHTML` property returns the HTML string inside of the element (text with HTML tags if any occur).

## Basic usage
```html
<div>Hello <strong>World!</strong></div> 
```

```javascript
const div = document.querySelector("div");
console.log(div.innerHTML); // "Hello <strong>World!</strong>"
```

## Security
If the string that you're rendering is coming from your users (for example, a string coming from a comment box that the user can fill), then you should **avoid** using `innerHTML` as your users will be able to write HTML & JavaScript code inside of your page which may lead to security issues. This is called Cross-Site Scripting (XSS) attack.