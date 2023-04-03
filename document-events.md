## -- DOMContentLoaded --
This event fires on the `document` element only. It signifies that the HTML has been loaded successfully by the browser. 

This means that the browser has finished reading all of the content of your HTML file. It doesn't mean however that images and other assets have finished loading.

```javascript
document.addEventListener("DOMContentLoaded", () => {
    console.log("DOM is ready");
});
```

## -- Scroll --
The scroll event triggers on any element that scrolls. It is often used on the `window` object as following:

```javascript
window.addEventListener("scroll", () => {
    console.log("page scrolled");
});
```

## -- other events --
1. `online` / `offline` – after establishing or loosing the net connection
2. `visibilitychange` – when document appears in window after switching tabs. The `document.visibilityState` takes value `visible` or `hidden`.
3. `dragstart` / `dragover` / `dragend` / `drop` – drag&drop API

## -- further reading --
1. [onscroll](https://javascript.info/onscroll)