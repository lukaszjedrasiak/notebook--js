## -- syntax --

```js
element.addEventListener(eventType, callback, [options])
```

This method allows you to wait for an event (let's say **click** for now) to happen on an `element`. Once that event occurs (the user clicks on the button), the `callback` function will execute.

### options
- `once`: if `true`, then the listener is automatically removed after it triggers. See: [once-event-listener](once-event-listener)
- `capture`: the phase where to handle the event. For historical reasons, `options` can also be `false/true`, that’s the same as `{capture: false/true}`.
- `passive`: if `true`, then the handler will not call `preventDefault()`.

## -- examples --

### Basic usage
```javascript
const button = document.querySelector("#app-button");

button.addEventListener("click", () => {
    // do something when the button is clicked.
    console.log("Button clicked");
});
```

### Disable button on click
```javascript
const button = document.querySelector("#app-button");

button.addEventListener("click", () => {
    button.setAttribute("disabled", "disabled");
});
```

### Delay log on click
```javascript
const button = document.querySelector("#app-button");

button.addEventListener("click", () => {
    setTimeout(() => {
        console.log("Hello World!");
    }, 2000);
});
```

### Show/hide sidebar
```js
// TODO: when the user clicks on '#menu-sidebar' => toggle the class 'show' on '#app-sidebar'

const button = document.querySelector('#menu-sidebar');
button.addEventListener('click', () => {
    document.querySelector('#app-sidebar').classList.toggle('show');
})
```

### Toggle dark mode
```js
// TODO: clicking on 'Toggle dark mode' should add/remove 'dark' class on <html>
const themeButton = document.querySelector('#theme-btn');
themeButton.addEventListener('click', () => {
    document.querySelector('html').classList.toggle('dark');
})
```

### Enable/disable button

```js
// TODO: Clicking on 'Disable start' should disable the 'Start' button and clicking on 'Enable start' should enable the 'Start' button.
const buttonStart = document.querySelector('#btn-start');
const buttonDisable = document.querySelector('#btn-disable');
const buttonEnable = document.querySelector('#btn-enable');

buttonDisable.addEventListener('click', () => {
    buttonStart.setAttribute('disabled', 'disabled');
})

buttonEnable.addEventListener('click', () => {
    buttonStart.removeAttribute('disabled');
})
```