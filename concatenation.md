## arrays concatenation
```javascript
const lat = [5.234];
const lng = [1.412];
const point = [...lat, ...lng];
console.log(point); // [5.234, 1.412];
```

```javascript
const items = ["Tissues", "Oranges"];

const otherItems = [...items, "Tomatoes"];
console.log(otherItems); // ["Tissues", "Oranges", "Tomatoes"]
```

## objects concatenation
```javascript
const firstPerson = {
    name: "Sam",
    age: 18
}

const secondPerson = {
    age: 25,
    type: "admin"
}

const mergedObjects = {...firstPerson, ...secondPerson};
console.log(mergedObjects); // {name: "Sam", age: 25, type: "admin"
```