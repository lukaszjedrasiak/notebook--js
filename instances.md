## creating instances

```js
class Rectangle{
    constructor(width, height) {
        this.width = width;
        this.height = height;
    }
}

const makeSquare = () => {
    return new Rectangle(10, 10);
};
```

## instance variables
An instance variable is a variable that belongs to a specific instance of a class. Instance variables can be used in class methods.

## methods
```js
	class ClassName {
    constructor(optionalParam) {
        console.log(`New class instance with param: ${optionalParam}`);

        // capturing constructor param into instance variable
        this.param = optionalParam;
    }

    // class method
    getParam() {
        return `passed param: ${this.param}`;
    }
    
    // calling method from other method
    upParam() {
        return this.getParam().toUpperCase();
    }
}

const instance = new ClassName("parametr");
console.log(instance.getParam());
```