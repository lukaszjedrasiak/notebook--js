### creating objects
```javascript
const user = {
    id: 1,
    firstName: "Sam",
    lastName: "Doe",
    age: 20
};
```

### read the value of a property in an object
```javascript
console.log(user.id);
```

### read dynamic property
```javascript
const user = {
    id: 1,
    name: "Sam Green",
    age: 20
};

const key = "id";
user[key]; // 1
```

### printing object content
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

### objects shorthand
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
### methods
[Object.keys()](object-keys)
[Object.values()](object-values)
[Object.entries()](object-entries)

[optional chaining](optional-chaining)
[nullish coalesing](nullish-coalescing)

[[immutability]]