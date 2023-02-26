## basic syntax

```javascript
array.filter(callback) //RETURNS new array that contains some of the items from the original array, based on the condition specified in callback function. Return keyword is neccessary.
```

## example

```js
const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door'];  
  
const shortWords = words.filter(word => {  
  return word.length < 6;  
});
```

`.filter()` method always returns an array:
- if one item matches the condition: an array with single element
- if no items match the condition: empty array