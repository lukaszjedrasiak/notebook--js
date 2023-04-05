## syntax

```js
str.indexOf(substr, pos)
```

It looks for the `substr` in `str`, starting from the given position `pos`, and returns the position where the match was found or `-1` if nothing can be found.

## examples

```js
let str = 'Widget with id';
alert( str.indexOf('Widget') ); // 0, because 'Widget' is found at the beginning
alert( str.indexOf('widget') ); // -1, not found, the search is case-sensitive
alert( str.indexOf("id") ); // 1, "id" is found at the position 1 (..idget with id)
```

If we’re interested in all occurrences, we can run `indexOf` in a loop. Every new call is made with the position after the previous match:

```js
let str = 'As sly as a fox, as strong as an ox';
let target = 'as'; // let's look for it let pos = 0;
while (true) {
	let foundPos = str.indexOf(target, pos);
	if (foundPos == -1) break;
	
	alert( `Found at ${foundPos}` );
	pos = foundPos + 1; // continue the search from the next position }
```

The same algorithm can be layed out shorter:

```js
let str = "As sly as a fox, as strong as an ox";
let target = "as";
let pos = -1;

while ((pos = str.indexOf(target, pos + 1)) != -1) {
	alert( pos );
}
```