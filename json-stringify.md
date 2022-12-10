JSON object => JSON string
```javascript
const person = {
    firstName: "Sam",
    lastName: "Green",
    age: 32
};
const string = JSON.stringify(person);
console.log(string); //'{"firstName":"Sam","lastName":"Green","age":32}'
```
