## -- event properties --
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

```js
const randomFunction = event => {
	const clickedElement = event.currentTarget;
    console.log(clickedElement.textContent);
}

button.addEventListener('click', randomFunction);
```

### other properties:
- `event.type` - property to access the name of the event.
- `event.clientX` / `event.clientY` – window-relative coordinates of the cursor.
- `event.target` – the deepest element in tree that originated the event.
- `timeStamp` – to access the number of millisecods that passed since the document loaded and the event was triggered.

## -- events types --
_An event_ is a signal that something has happened. All DOM nodes generate such signals (but events are not limited to DOM).

1. [mouse events](mouse-events)
2. [keyboard events](keyboard-events)
3. [form events](form-events)
4. [document events](document-events)
5. [css events](css-events)
6. [pointer events](pointer-events)

## -- events handlers --
### HTML attribute
```html
<input type="button" onlick="function()" value="sth">
```

### DOM property
```js
element.onclick = function() {
	// do sth
};
```

If we want to call existing function we need to assign it without parentheses:
```js
function something() {
	// do sth
};

element.onlick = something;
```

### addEventListener

Using the `.addEventListener()` method, we can have a DOM element listen for a specific event and execute a block of code when the event is detected. The DOM element that listens for an event is called the _event target_ and the block of code that runs when the event happens is called the _event handler_.

This method is a way to add multiple handlers for one event (i.e. highlight a button and show message after a click): 
- [addEventListener](addEventListener)
- [removeEventListener](removeEventListener)

### preventing browser actions
```html
<a href="/" onclick="return false">Click here</a>
or
<a href="/" onclick="event.preventDefault()">here</a>
```

## -- links --
1. https://javascript.info/introduction-browser-events

## -- further reading --
1. [bubbling and capturing](https://javascript.info/bubbling-and-capturing)
2. [event delegation](https://javascript.info/event-delegation) - how to add the same handling for many similar elements and check the event.target.
3. [custom events](https://javascript.info/dispatch-events)