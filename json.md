JSON stands for JavaScript Object Notation. It's a format for storing and sending data.

Example:
```javascript
{
    "firstName": "Sam",
    "lastName": "Green",
    "age": 24
}
```

JSON is a subset of JavaScript objects. This means that every JSON object **is** a JavaScript object whereas not every JavaScript object is a JSON object. I.e.: JS object with function **is not** JSON.

The reason why this is the most frequent use case is that when you communicate with an API, you cannot send an object. You will have to convert it to a string. Similarly, the API cannot send you an object, it will send you a string. But, that string is not any string. It's a JSON string. That means that it can be converted back into a JSON object.

## json operations
[json.parse(string)](json-parse)
[json.stringify(object)](json-stringify)