## syntax

```js
array.splice(start[, deleteCount], [insertedItems]);
```

This method:
- Removes `deleteCount` items from the array starting from the `start` index. If `deleteCounts` is not provided, method will remove **all** items from the `start` index to the end of the array.
- Pastes the `insertedItems` just behind the `start` element
- Returns an array of removed items.

## example

```js
let data = [0, 1, 2, 3, 4, 5];
let tmp = data.splice(1, 4, "a", "b");

console.log(data) // [0, "a", "b", 5]
console.log(tmp) // [1, 2, 3, 4]
```