If you need to add an event listener that only runs once, there's an easier way instead of adding an event listener and then removing it. You can add an event listener and specify `once: true` in its options.

```javascript
const button = document.querySelector("button");

button.addEventListener("click", () => {
    console.log("button clicked");
}, {
    once: true
});
```

Notice the 3rd argument for `addEventListener` which is an object. `{once: true}` means that the event should execute only once and then it gets automatically removed.

After the user clicks on the button the first time, the event listener will be automatically removed by the browser.