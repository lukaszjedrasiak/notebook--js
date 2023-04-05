[[template strings]]

## Properties
- string.length;

## Methods
- .charAt()
- .charCodeAt()
- [.codePointAt()](codePointAt)
- .concat()
- [.includes()](includes)
- [.indexOf()](indexOf)
- .lastIndexOf() – works as a `indexOf()` method but searches from the end of a string to its beginning.
- localeCompare() – compares two strings with the rules according to given or system language.
- .normalize()
- .padEnd()
- .padStart()
- [.parseInt()](parseInt)
- [.repeat()](repeat)
- [replace()](replace)
- [replaceAll()](replaceAll)
- [.split()](split)
- [.startsWith() / endsWith()](startsWith_endsWith)
- [.substr](substr)
- [.substring()](substring)
- .slice() – works very similar to `substring()` method. Negative values are supported. Is shorter to write, so it is recommended over `substring`.
- .split()
- .toLowerCase();
- .toUpperCase();
- [.trim()](trim)
- .trimEnd()
- .trimStart()

## String methods
- `String.fromCodePoint(code)` – returns a character by its numeric `code`

## Character access
Square bracket syntax
```javascript
string[0]; //first character
string[string.length - 1] // last character
string[-1] // undefined
```

.at(index) method
``` javascript
string.at(0); //first character
string.at(-1); //last character
```

Strings are iterable. It means that you can iterate each character inside string with `for/of` loop or `...`

```js
let str = "random string";
for (let char of str) {
	console.log(char);
}
```