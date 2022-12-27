Naming convention: UpperCamelCase

## creating class
```js
class ClassName {
    constructor(optionalParam) {
        console.log(`New class instance with param: ${optionalParam}`);
    }
}

const instance = new ClassName("parametr");

```

## old way of creating classes
```javascript
//This is the constructor
function Rectangle(width, height) {
    this.width = width;
    this.height = height;
}

// this is an instance method (that you can call on new instances of Rectangle)
// Note: this has to be a function (not an arrow function), will be explained later on in Lexical scope
Rectangle.prototype.isSquare = function() {
    return this.width === this.height;
}
```

[[instances]]
[[getters-setters]]
[[static methods]]
[[methods chaining]]
[[class inheritance]]

[[public fields]]
[[private fields]]
