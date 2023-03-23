[[template strings]]

## Properties
- string.length;

## Methods
- .charAt()
- .charCodeAt()
- .codePointAt
- .concat()
- [.includes()](includes)
- .indexOf()
- .lastIndexOf()
- .normalize()
- .padEnd()
- .padStart()
- [.parseInt()](parseInt)
- [replace()](replace)
- [replaceAll()](replaceAll)
- [.split()](split)
- [.startsWith() / endsWith()](startsWith_endsWith.md)
- [.substring()](substring)
- .slice()
- .split()
- .toLowerCase();
- .toUpperCase();
- [.trim()](trim)
- .trimEnd()
- .trimStart()

## Character access
Square bracket syntax
```javascript
string[0]; //first character
```

.at(index) method
``` javascript
string.at(0); //first character
string.at(-1); //last character
```

How to access to the last string character?
``` javascript
string.at(-1);
string[string.length - 1];
```

Strings are iterable. It means that you can iterate each character inside string with `for/of` loop or `...`

