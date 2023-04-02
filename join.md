This method:
- changes each element into string,
- joins the strings into one string,
- optionally - delimits them with `delimiter`
- returns the final string.

It is the opposite of the string [split](split) method, which is making an array from the given string.

## syntax

```javascript
array.join(delimiter) // returns a string of the array elements separated by the delimiter
```

The result of this method called without the argument is the same as this one:
```js
array.toString()
```

## example

```js
let data = [1, 2, 3, 4, 5]
data.join("-") // => "1-2-3-4-5"
```