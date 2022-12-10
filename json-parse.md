JSON string => JSON object

```javascript
const string = '{"firstName":"Sam","lastName":"Green","age": 32}';
const person = JSON.parse(string); // {firstName: "Sam", lastName: "Green", age: 32}
console.log(person.firstName); // "Sam"
```

This function is synchronous. This means that it will block the main thread of JavaScript. So, assuming you had a very long response from an API (several MBs), then the browser will become unusable for a second or two. This is not good.