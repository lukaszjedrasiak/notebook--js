```javascript
array.map(callback) // RETURNS transformed array
```

## examples
double values
```javascript
const numbers = [4, 2, 5, 8];

const doubled = numbers.map(number => number * 2);
```

extract provided field from array of objects

```javascript
const users = [{
    id: 1,
    name: "Sam Doe"
}, {
    id: 2,
    name: "Alex Blue"
}];

const csv = users.map(user => user.name).join(", ");
console.log(csv);
```

convert array of arrays into HTML table
```javascript
const rows = [[Carbs, 17g], [Protein, 19g], [Fat, 5g]];

const renderTableRows = rows => {
    console.log(rows);
    return rows.map(row => {
        return `<tr>
        <td>${row[0]}</td>
        <td>${row[1]}</td>
        </tr>`
    }).join("");
}
```