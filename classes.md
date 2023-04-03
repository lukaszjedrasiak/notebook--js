> Classes are templates for objects.

A class in JavaScript is a collection of objects inheriting properties from the same prototype. Defining a class in JS involves defining the prototype.

Naming convention: UpperCamelCase

## creating class

JavaScript calls the `constructor()` method every time it creates a new _instance_ of a class.

```js
class ClassName {
    constructor(optionalParam) {
        console.log(`New class instance with param: ${optionalParam}`);
    }
}
```

An _instance_ is an object that contains the property names and methods of a class, but with unique property values.

```js
const instance = new ClassName("parameter");
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

## short summary

-   _Classes_ are templates for objects.
-   Javascript calls a _constructor_ method when we create a new instance of a class.
-   _Inheritance_ is when we create a parent class with properties and methods that we can extend to child classes.
-   We use the `extends` keyword to create a subclass.
-   The `super` keyword calls the `constructor()` of a parent class.
-   Static methods are called on the class, but not on instances of the class.
