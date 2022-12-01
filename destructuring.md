## array destructuring
Destructuring means assigning array items into variables.

Classic syntax:
```javascript
const dimensions = [20, 5]

// create variables
const width = dimensions[0];
const height = dimensions[1];

// log them
console.log(width); //20
console.log(height); //5
```

Destructuring sugar syntax

```js
const dimensions = [20, 5];

// create variables
const [width, height] = dimensions;

// log them
console.log(width); //20
console.log(height); //5
```

## objects destructuring
Classic syntax
```js
const config = {
    id: 1,
    isAdmin: false,
    theme: {
        dark: false,
        accessibility: true
    }
};

const id = config.id;
const isAdmin = config.isAdmin;
const theme = config.theme;
```

Sugar syntax
```js
const {id, isAdmin, theme} = config;
```

Sugar syntax with default value
```js
const {id, isAdmin = false, theme} // default works only when key do not exist in object
```

Sugar syntax with renaming values
```js
const {id, isAdmin: newVariableName, theme};
```