## submit
By default, the browser will send the data to the current page. To avoid that, you need to prevent the default action with `event.preventDefault()`.

```javascript
const form = document.querySelector("#address-form");

form.addEventListener("submit", event => {
    // avoid reloading the page
    event.preventDefault();
});
```

## focus / blur
The `focus` and `blur` events are often used in form validation. They let you know when a user _focuses_ (put the cursor inside of it) on a textbox and when they remove the focus (`blur`).

The word `focus` means that the element is selected to receive user input from the keyboard. If you write something on your keyboard, it will be written inside the element that is focused.  
When you remove the focus, then this will dispatch a `blur` event.

You can listen to both of these events on text boxes. Let's see an example:

```html
<input type="text" id="name" placeholder="Enter your name">
```

```javascript
const name = document.querySelector("#name");

name.addEventListener("focus", () => {
    console.log("user focused inside the name");
});

name.addEventListener("blur", () => {
    console.log("user removed focus from the name");
});
```

## change
The `change` event is often used on the `<select>` element. It lets you know when the user has selected a new choice.

```html
<select id="countries">
    <option value="">Select a country</option>
    <option value="NL">Netherlands</option>
    <option value="BR">Brazil</option>
</select>
```

```javascript
const countries = document.querySelector("#countries");

countries.addEventListener("change", () => {
    console.log(countries.value);
});
```