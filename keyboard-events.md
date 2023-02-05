## keydown / keyup

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

### properties
- `event.key` – store the character (it ditinguish small caps and all caps)
- `event.code` – store the 'physical key code' (i.e. KeyZ)