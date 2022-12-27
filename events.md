[[addEventListener]]
[[removeEventListener]]
[[once event listener]]

## events details

When the user clicks that element, we can run a callback. This callback will receive from the browser one argument. We call this argument: event details.

The event details contains information about the event that has just occurred. For example, for a click event:
- The X (horizontal) position of the mouse when the click was triggered.
- The Y (vertical) position of the mouse when the click was triggered.
- The time when the click was triggered.
- A boolean representing whether the ctrl key was pressed when the click was triggered.
- A boolean representing whether the shift key was pressed when the click was triggered.

You will (almost) never use the information above. However, there is one property that you will use quite often. This property is called currentTarget. We'll learn about this in the next lesson.

### event.currentTarget
The `event.currentTarget` refers to the **element to which the event listener has been attached**.

```javascript
button.addEventListener("click", event => {
    const clickedElement = event.currentTarget;
    console.log(clickedElement.textContent);
});
```

## events types
### click

### submit
By default, the browser will send the data to the current page. To avoid that, you need to prevent the default action with `event.preventDefault()`.

```javascript
const form = document.querySelector("#address-form");

form.addEventListener("submit", event => {
    // avoid reloading the page
    event.preventDefault();
});
```

### focus/blur
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

### DOMContentLoaded
This event fires on the `document` element only. It signifies that the HTML has been loaded successfully by the browser. 

This means that the browser has finished reading all of the content of your HTML file. It doesn't mean however that images and other assets have finished loading.

```javascript
document.addEventListener("DOMContentLoaded", () => {
    console.log("DOM is ready");
});
```

### Scroll
The scroll event triggers on any element that scrolls. It is often used on the `window` object as following:

```javascript
window.addEventListener("scroll", () => {
    console.log("page scrolled");
});
```

### change
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

### keydown/keyup

The `keydown` and `keyup` events are used to know when the user has typed a character on the keyboard. These can be used to implement keyboard shortcuts.

The only difference between `keydown` and `keyup` is that `keydown` triggers while the user starts pressing the button and before the character is being typed. On the other hand, `keyup` fires after the character has been typed.

For most scenarios, you end up needing `keyup`. These events can be either added to the `document` (to know when a user has pressed a key anywhere on the page) or inside a textbox.

```javascript
document.addEventListener("keydown", event => {
    console.log(event.key);
});

document.addEventListener("keyup", event => {
    console.log(event.key);
});
```
