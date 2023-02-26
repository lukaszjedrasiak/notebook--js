**Defining getters and setters in a class is _mostly_ used to validate or modify certain values before they are set as properties on a class.**

## summary

1. Add an underscore (`_`) as a prefix of property name to show that it is private property, i.e. `_property`.
2. Add a setter method to allow editing private property, i.e. `object.setterName = value`. Although, property can be still accessed without setter: `object._property = value`.
3. Add a getter method to get the value of private property, i.e. `variable = object.getterName`.
4. See that - event setters and getters are methods - we call them without parentheses.

### Setter

Defining getters and setters in a class is _mostly_ used to validate or modify certain values before they are set as properties on a class. There are other use cases. We'll also cover the use case in front-end frameworks/libraries.

Let's take an example where we'd like to create a class `User` that has an `age` property. However, we'd like to always make sure that this `age` property is a number. For that, we define a **setter** for the `age` property. Here's what the setter looks like:

```javascript
class User {
    set age(value) {
        console.log("age setter");
        this._age = Number.parseInt(value, 10);
    }
}
```

We've added a `console.log("age setter")` so that you can see when this setter gets called.  
Inside this setter, we're converting the `value` to a number (with `Number.parseInt(string, 10)`), and then we set the result on a new instance variable called `this._age`.

The `_` here in `_age` is a convention meaning that this property is internal to the class and should not be accessed from outside. JavaScript recently introduced private fields, however, sufficient browser support is not there yet.

This is very important. If you accidentally set the result on `this.age`, then you end up creating an infinite loop. That's because whenever you try to access `this.age`, JavaScript will automatically call this setter. So you end up with a function that keeps calling itself forever.

Let's see how we can use the class that we defined above:

```javascript
const user = new User();
user.age = "18";
console.log(user); // {_age: 18}
```

Notice how we are able to set the `age` property on the `user` instance by setting `user.age =`  to a certain value.  
In this example, we set it to a string `"18"`, which then gets converted to a number by the setter. So, setting `user.age =`  will call the `set age(value)` function and the `value` will receive the string `"18"`.

This setter will then create a new instance variable called `_age` and set it to `18` (as a number).

## Getter

**That should be your main takeaway here, a getter is just a computed property, which is why you can access it with a dot and you don't have to call it as if it were a method.**

> In other words - getters are called without parentheses.

The remaining problem is that if we try to access `user.age`, we get `undefined`. That's because we have not defined a `getter` for the `age` property.

Let's go ahead and define a **getter** for the `age` property. We do that by defining a `get age()` function as follows:

```javascript
class User {
    get age() {
        console.log("age getter");
        return this._age;
    }

    set age(value) {
        console.log("age setter");
        this._age = Number.parseInt(value, 10);
    }
}
```

With the class definition above, here's how we can use it:

```javascript
const user = new User();
user.age = "20"; // calls set age(value)
console.log(user.age); // calls get age(), returns 20 (number)
```

Another use case for getters is to change the formatting of a property before returning it. We'll see that in one of the following challenges.

You may have noticed that the `setter` receives a `value` whereas the `getter` doesn't. This is because the `value` (or any parameter name you choose) provided to the setter is the value written after the equal sign. However, for the `getter`, there is no equal sign. You're only reading the value.