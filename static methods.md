Example:
```javascript
console.log(Config.getYear()); // for example, 2025

class Config {
    static getYear() {
        // code to get the current year (for example, 2025)
        const date = new Date();
        return date.getFullYear();
    }
}
```

- Is the result of this method the same across all instances of the class? If yes, then it should be `static`.
- Is the method not accessing any instance variable of this class? If yes, then most likely it should be `static`.