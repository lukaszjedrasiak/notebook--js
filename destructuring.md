Destructuring is a way to unpack values from arrays and objects and assign them to variables or parameters.

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

Storing redundant values
```js
let [x, ...y] = [1, 2, 3, 4]
console.log(x) // => 1
console.log(y) // => [2, 3, 4]
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

### usage

```js
let o = {
	x: 1,
	y: 2
}

for (conts [name, value] of Object.entries(0)) {
	console.log(name, value)
}
```

## destructuring function parameters

```js
let truck = {  
  model: '1977 Mustang convertible',  
  maker: 'Ford',  
  city: 'Detroit',  
  year: '1977',  
  convertible: true  
};  
  
const printCarInfo = ({model, maker, city}) => {  
  console.log(`The ${model}, or ${maker}, is in the city ${city}.`);  
};  
  
printCarInfo(truck);  
// Prints: The 1977 Mustang convertible, or Ford, is in the city Detroit.
```