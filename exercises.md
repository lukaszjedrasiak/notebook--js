[factorial with tdd tests](factorial-with-tests)

## reverseArray()

Write a function, `reverseArray()`, that takes in an array as an argument and returns a new array with the elements in the reverse order.

```js
const reverseArray = sentence => {
  const reversedSentence = [];
  for (let i = sentence.length - 1; i >= 0; i--) {
    reversedSentence.push(sentence[i]);
  }
  return reversedSentence;
}
```

## greetAliens()

Write a function, `greetAliens()`, that takes in an array of strings and uses a `for` loop to print a greeting with each string in the array.

The greeting should take the following format: “Oh powerful [stringElement], we humans offer our unconditional surrender!”

```js
const greetAliens = aliens => {
  for (index in aliens) {
    console.log(`Oh powerful ${aliens[index]}, we humans offer our unconditional surrender!`);
  }
}
```

## convertToBaby()

Write a function, `convertToBaby()`, that takes in an array as an argument and, using a loop, returns a new array with each string in the array prepended with `'baby '`. Note: You may have noticed how convenient it would be to use `map`, but you’re not allowed to use it here.

```js
const convertToBaby = array => {
  const newArray = [];
  for (index in array) {
    newArray.push('baby ' + array[index])
  }
  return newArray;
}
const animals = ['panda', 'turtle', 'giraffe', 'hippo', 'sloth', 'human'];
console.log(convertToBaby(animals))
```

## shoutGreetings()

Write a function `shoutGreetings()` that takes in an array of strings and returns a new array. This new array should contain all the strings from the argument array but with capitalized letters and an exclamation point appended to the end: `'heya'` will become `'HEYA!'`

```js
const shoutGreetings = arr => arr.map(item => item.toUpperCase() + '!')
const greetings = ['hello', 'hi', 'heya', 'oi', 'hey', 'yo'];
console.log(shoutGreetings(greetings))
```

## sortYears()

Write a function `sortYears()` that takes in an array of years, and, using the built-in `.sort()` method, returns that array with the years sorted in descending order.

```js
function sortYears(years) {
	years.sort(function(a, b) {
    return b - a;
  });
  return years;
}
```

## justCoolStuff()

Write a function `justCoolStuff()` that takes in two arrays of strings, and, using the built-in `.filter()` method, returns an array with the items that are present in both arrays.

```js
const justCoolStuff = (firstArray, secondArray) => firstArray.filter(item => secondArray.includes(item));
```

## isTheDinnerVegan()

Write a function `isTheDinnerVegan()` that takes in an array of food objects and returns a boolean value based on whether or not every item in the array has entirely `plant`-based origins.

```js
const isTheDinnerVegan = arr => {
  return arr.every(item => item.source === 'plant')
}

const dinner = [{name: 'hamburger', source: 'meat'}, {name: 'cheese', source: 'dairy'}, {name: 'ketchup', source:'plant'}, {name: 'bun', source: 'plant'}, {name: 'dessert twinkies', source:'unknown'}];  

console.log(isTheDinnerVegan(dinner)) // Should print false
```

## sortSpeciesByTeeth()

Write a function `sortSpeciesByTeeth()` that takes in an array of species and sorts the array in ascending order based on the average number of teeth that species possesses (`numTeeth`) .

```js
const speciesArray = [ {speciesName:'shark', numTeeth:50}, {speciesName:'dog', numTeeth:42}, {speciesName:'alligator', numTeeth:80}, {speciesName:'human', numTeeth:32}];

const sortSpeciesByTeeth = arr => {
  return arr.sort((a, b) => a.numTeeth - b.numTeeth);
}

console.log(sortSpeciesByTeeth(speciesArray))
```

## subLength()

Write a function `subLength()` that takes 2 parameters, a string and a single character. The function should search the string for the two occurrences of the character and return the length between them including the 2 characters. If there are less than 2 or more than 2 occurrences of the character the function should return 0.

```js
const subLength = (str, chr) => {
  const arr = str.split("");
  const index1 = arr.indexOf(chr);
  const index2 = arr.indexOf(chr, index1+1);
  const index3 = arr.indexOf(chr, index2 +1)

  if ((index1 === -1) || (index2 === -1) || (index3 !== -1)) {
    return 0
  } else {
    return index2 - index1 + 1;
  }
}

subLength('Saturday', 'a'); // returns 6  
subLength('summer', 'm'); // returns 2  
subLength('digitize', 'i'); // returns 0  
subLength('cheesecake', 'k'); // returns 0
```