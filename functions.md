Basic function
```javascript
function sum(x, y) {
    return x + y;
}
```

Function with default parameters
```javascript
function sum(x = 0, y = 0) {
    return x + y;
}
```

[[arrow functions]]

### Returning booleans
Standard shape
```javascript
function isPassing(grade) {
    if (grade >= 10) {
        return true;
    } else {
        return false;
    }
}
```

Shorter shape
```javascript
function isPassing(grade) {
    return grade >= 10;
}
```

[[functions callbacks]]
