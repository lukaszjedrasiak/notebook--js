This older way of creating classes is useful when you want to inherit only _some_ of the `methods` - not all of them.

```javascript
//constructor functions
function Gorilla() {
}
function Banana() {
}
function GorillaBanana() {
}

Gorilla.prototype.eat = function() {
    // ...
}

Banana.prototype.peel = function() {
    // ...
}

// Extend our GorillaBanana with the Gorilla's eat() method
GorillaBanana.prototype.eat = Gorilla.prototype.eat;

// Extend our GorillaBanana with Banana's peel() method
GorillaBanana.prototype.peel = Banana.prototype.peel;
```

You can also mix all of these syntaxes in the following way:
```javascript
class Gorilla {
    // define methods here
}
class Banana {
    // define methods here
}
class GorillaBanana {
    // do not use 'extends' because we'd like to choose the methods one by one
}

// Extend our GorillaBanana with the Gorilla's eat() method
GorillaBanana.prototype.eat = Gorilla.prototype.eat;

// Extend our GorillaBanana with Banana's peel() method
GorillaBanana.prototype.peel = Banana.prototype.peel;
```
## summary
In summary, classical inheritance is a lot more popular than prototypal inheritance.  
However, prototypal inheritance is more powerful because it allows us to choose which methods we'd like to inherit.

JavaScript supports prototypal inheritance. For that, you'd need to add methods to the `.prototype` object.

When you use the `extends` keyword, JavaScript simulates classical inheritance by copying all the methods. This is the behavior that is most commonly used.

In closing, you will rarely ever change the prototype object and you will almost always inherit using `extends`. This lesson describes how things work under the hood, which can be quite confusing!