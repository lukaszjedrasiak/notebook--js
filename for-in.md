This loop is used to iterate over **objects**.

## example
```javascript
const person = {
    id: 1,
    name: "Alex"
};

for (const key in person) {
    console.log(key);
    console.log(person[key]);
}
```