To read the written content of an `input`, `select` or `textarea` element, you have to use `value` property:

```html
<form>
    <input type="email" id="email" placeholder="Enter your email">
    <input type="submit" value="Register">
</form>
```

```javascript
const email = document.querySelector("#email");
console.log(email.textContent); // undefined ❌ (there's no closing tag)
console.log(email.value); // text written in the email field
```