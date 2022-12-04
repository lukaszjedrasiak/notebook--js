```js
const grades = [10, 20];
const gradesCopy = [...grades];
gradesCopy.push(30);
const gradesCopyCopy = [...gradesCopy, 69];
console.log(`original: ${grades}`);
console.log(`copy: ${gradesCopy}`);
console.log(`copy copy: ${gradesCopyCopy}`);
```

This copy is called shallow copy because it only goes 1 level deep. This means that for an array of objects if you make an update to the objects in the new array, the objects in the old array will **still be updated**.

In the context of arrays of objects, 1 level deep means that the objects in the new array will still refer to the same objects in the original array.

