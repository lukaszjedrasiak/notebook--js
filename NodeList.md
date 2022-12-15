**A NodeList is not an array**. However, there are some similarities:

-   they both have a `length` property (you can access it with `.length`)
-   you can access items at a specific index with the square brackets. For example, `[0]` and `[1]`.
-   you can [iterate](https://learnjavascript.online/app.html?id=1803#) through both of them with `.forEach()`.

## Convert NodeList to Array

```javascript
const divs = document.querySelectorAll("div"); // NodeList
const items = [...divs]; // Array
```

Or, in a single line:

```javascript
const items = [...document.querySelectorAll("div")]; // Array
```

As you can see, you can convert a NodeList into an array using the array spread syntax (`...`) which spreads every single item of the NodeList, into a new array.