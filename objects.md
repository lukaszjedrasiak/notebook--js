Objects are _passed by reference_. This means when we pass a variable assigned to an object into a function as an argument, the computer interprets the parameter name as pointing to the space in memory holding that object. As a result, functions which change object properties actually mutate the object permanently (even when the object is assigned to a `const` variable).

If we assign an object to variable like this:
```js
y = obj;
```
we do not copy an object to `y` variable, but we assign a reference. So if we make changes to the `y` variable we change the `obj`.

In other words: when we make changes to an object passed into a function, those changes are permanent.

## comparing objects

Objects are not being compared on the _value_ basis. Two objects are different even though they have the same values inside. The same is for arrays.

```js
let o = {x: 1}
let p = {x: 1}

x === p //false
```

Objects are being compared on the _reference_ basis. Two values are the same if they reference to the same object.

```js
let o = {x: 1}
let p = o
o.x = 2

p === o // true
```

## creating objects

### single object

Object literals:
```javascript
const user = {
    id: 1,
    firstName: "Sam",
    lastName: "Doe",
    age: 20
};
```

`new` operator:
```js
let o = new Object() // {} equivalent
let a = new Array() // [] equivalent
let d = new Date()
let r = new Map()
```

function `Object.create()`
```js
let ol = Object.create({x: 1, y: 2});
```

### multiple objects

In order to create many instances on an object we can use _factory functions_. This kind of function returns an object with parameters given as function arguments.

Basic example:
```js
const monsterFactory = (name, age, energySource, catchPhrase) => {  
  return {   
    name: name,  
    age: age,  
    energySource: energySource,  
    scare() {  
      console.log(catchPhrase);  
    }  
  }  
};

const ghost = monsterFactory('Ghouly', 251, 'ectoplasm', 'BOO!');  
ghost.scare(); // 'BOO!'
```

Shorter syntax, called also [destructuring](destructuring)
```js
const monsterFactory = (name, age, energySource, catchPhrase) => {  
  return {   
    name,  
    age, 
    energySource,  
    scare() {  
      console.log(catchPhrase);  
    }  
  }  
};

const ghost = monsterFactory('Ghouly', 251, 'ectoplasm', 'BOO!');  
ghost.scare(); // 'BOO!'
```

## object properties

`delete` operator – removes the property of an object (only self-properties, not inherited).
```js
delete book.author;
delete book["title"]
```

`in` operator – checks if given property is in object.
```js
let obj = {x: 1};
"x" in obj; // true
"y" in obj; // false
"toString" in obj; // true - it is inherited property
```

`hasOwnProperty()` method – works as `in` operator but returns `false` if given property is inherited.
```js
let obj = {x: 1};
obj.hasOwnProperty("x"); // true
obj.hasOwnProperty("y"); // false
obj.hasOwnProperty("toString") // false - inherited property
```

alternative way of checking property existence:
```js
let obj = {x: 1};
obj.x !== undefined // true
obj.y !== undefined // false
obj.toString !== undefined // true
```

### copying properties from object to object

```js
let position = {x: 0, y: 0};
let dimensions = {width: 100, height: 75};
let rect = {...position, ...dimensions}
```

## reading object values

### dot notation

```javascript
console.log(user.id);
```

### bracket notation

```javascript
console.log(user['id'])
```

In bracket notation you can pass the `key` name by the variable. It allows to read dynamic properties.

```javascript
const user = {
    id: 1,
    name: "Sam Green",
    age: 20
};

const key = "id";
user[key]; // 1
```

This approach can be helpful when working with functions.

```js
let returnAnyProp = (objectName, propName) => objectName[propName];  
returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```

## printing object content
```js
const settings = {
    theme: "Dark",
    version: "2.4.1",
    beta: false
};

const keys = Object.keys(settings);
console.log(keys);

keys.forEach(key => {
    console.log(`${key}: ${settings[key]}`);
})

//shorert form
Object.keys(settings).forEach(key => console.log(`${key}: ${settings[key]}`));
```

### nested objects
```js
	for (let crewMember in spaceship.crew) {
	console.log(`${spaceship.crew[crewMember].name}: ${spaceship.crew[crewMember].degree}`)
}
```

## objects shorthand
```js
const id = 1;
const name = "bob";

const user = {
	id, name
};

// {id: 1, name: bob}
```

```js
const x = 0;

console.log(x); // 0
console.log({x}); // x: 0
```

## mutability

Objects are mutable, but on some reason I put a link here to: [[immutability]]

It’s important to know that although we can’t reassign an object declared with `const`, we can still mutate it, meaning we can add new properties and change the properties that are there.

```js
object.newProperty = newValue;
object[newerProperty] = newerValue
```

Delete property
```js
delete object.anyProperty;
```

### private properties

If we want to express that some properties can be mutated only by object methods we can name them in this way:
```js
obj = {
	_privateProperty: value,
}
```

Although, the name itself is not enough – we need also declare [getters and setters](getters-setters)

## methods

> A property is what an object has, while a method is what an object does.

### declaring methods

Basic syntax:
```js
anyObject = {
	someName: function () {
		//function body here
	}
}
```

Syntax from ES6:
```js
anyObject = {
	someName () {
		//function body here
	}
}
```

### calling object methods

```js
anyObject.someName();
```

### built-in methods

[Object.keys()](object-keys)
[Object.values()](object-values)
[Object.entries()](object-entries)
[Object.assign](object-assign)
obj.toString() – converts an `obj` to string

## chaining nested objects

Example
```js
spaceship.nanoelectronics['back-up'].battery; // Returns 'Lithium'
```

See also: [optional chaining](optional-chaining)

## miscelaneous

[nullish coalesing](nullish-coalescing)
[[built-in objects]]
[this keyword](this-keyword)
[constructor-new](constructor-new)