## example
```javascript
const people = ["Sam", "Alex"];

for (const person of people) {
    console.log(person);
}
```

## benefits
1.  The Syntax (it all comes down to your personal preference if you prefer this over `.forEach()`)
2.  Being able to use the `break` and `continue` keywords.

## usage
The for...of works not only on arrays but on all data types and variables that are "iterable". Iterable means data types that you can iterate over. The list includes:
- Strings,
- Arrays,
- NodeList (the result of document.querySelectorAll),
- Map,
- Set.