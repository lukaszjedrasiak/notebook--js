## click
When the mouse clicks on an element (touchscreen devices generate it on a tap).

A left-button click first triggers `mousedown`, when the button is pressed, then `mouseup` and `click` when it’s released.
...

## dblclick
Triggers after two clicks on the same element within a short timeframe. This event is triggered after `mousedown` --> `mouseup` --> `click` sequence triggered twice.

## contextmenu
When the mouse right-clicks on an element. There are other ways to open a context menu, e.g. using a special keyboard key, it triggers in that case also, so it’s not exactly the mouse event.
...

## -- mouseover / mouseout --
When the mouse cursor comes over / leaves an element.

### related target
For `mouseover`:
-   `event.target` – is the element where the mouse came over.
-   `event.relatedTarget` – is the element from which the mouse came (`relatedTarget` → `target`).

For `mouseout` the reverse:
-   `event.target` – is the element that the mouse left.
-   `event.relatedTarget` – is the new under-the-pointer element, that mouse left for (`target` → `relatedTarget`).

## - mouseenter / mouseleave --
Events `mouseenter/mouseleave` are like `mouseover/mouseout`. They trigger when the mouse pointer enters/leaves the element.

But there are two important differences:
1.  Transitions inside the element, to/from descendants, are not counted.
2.  Events `mouseenter/mouseleave` do not bubble.

## -- mousedown / mouseup --
When the mouse button is pressed / released over an element.

### button property
The possible values of `event.button` are:
| button state | value |
| ------------ | ----- |
| Left button (primary) | 0 |
| Middle button (auxiliary) | 1 |
| Right button (secondary) | 2 |
| X1 button (back) | 3 |
| X2 button (forward) | 4 |

### modifiers properties
All mouse events include the information about pressed modifier keys. They are `true` if the corresponding key was pressed during the event. Event properties:
-   `shiftKey`: Shift
-   `altKey`: Alt (or Opt for Mac)
-   `ctrlKey`: Ctrl
-   `metaKey`: Cmd for Mac

Example:
```js
button.onclick = function(event) {
	if (event.altKey && event.shiftKey) {
		alert('Hooray!');
	}
};
```

## mousemove
Every mouse move over an element triggers that event.

## -- common properties --
### coordinates
All mouse events provide coordinates in two flavours:
1.  Window-relative: `clientX` and `clientY`.
2.  Document-relative: `pageX` and `pageY`.

## -- further reading --
1. [mouse events basics](https://javascript.info/mouse-events-basics)
2. [mouse drag-and-drop](https://javascript.info/mouse-drag-and-drop)