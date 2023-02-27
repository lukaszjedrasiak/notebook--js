```javascript
const button = document.querySelector("button");

const handleClick = () => {
    console.log("button clicked");    
}

button.addEventListener("click", handleClick);
button.removeEventListener("click", handleClick);
```

The content of `removeEventListener` must be exactly the same as `addEventListener` - this is why the callback was wrapped by separate function.

> If `.addEventListener()` was provided an anonymous function, then that event listener cannot be removed.

If you do use the `()` (`button.addEventListener("click", handleClick());// ❌`, the function `handleClick` will be called on page load and the event listener will not work.