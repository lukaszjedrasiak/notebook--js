```javascript
1 === 1; //true
27 === 27; //true
"hello world" === "hello world"; //true
"welcome" === "welcome"; //true
true === true; //true
false === false; //true (because they're the same)
```

```javascript
1 === 1; //true
27 === 27; //true
"hello world" === "hello world"; //true
"welcome" === "welcome"; //true
true === true; //true
false === false; //true (because they're the same)
```

As in, we expected `[] === []` to be true because they are both empty arrays, but the way JavaScript works is different as it's checking if they are the same instance.

IMPORTANT
```javascript
const firstArray = [];
const secondArray = firstArray; // secondArray now points to firstArray
console.log(firstArray); // []
console.log(secondArray); // []

firstArray.push(10);
console.log(firstArray); // [10]
console.log(secondArray); // [10]
```

**This means `firstArray` and `secondArray` are now referring to the same value. Technically we say they are referencing the same place in the memory.**

When you assign a variable to an object or array, it does NOT copy it. It will only reference its value. It means, that we have to use another way  - [[shallow-copy]] - in order to clone an `array` or `object` and be able to changing the values in the new instances.

So whenever you change the value in any of the 2 variables, then both `firstArray`, and `secondArray` will return the same value that has been updated.

Similar behaviour with objects.
###  updating the property in object copy
You can update an existing property: `{...originalObject, property: 'newValue'}`

### object destructuring with deleting property
```javascript
const book = {
    id: 1,
    title: "Harry Potter",
    year: 2017,
    rating: 4.5
}

// GOOD: immutable
const {year, ...rest} = book;
console.log(rest); // { id: 1, title: "Harry Potter", rating: 4.5}
```

