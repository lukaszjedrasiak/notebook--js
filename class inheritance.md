**When a "child" class inherits from a "parent" class, the "child" class will automatically get all the methods defined on the "parent" class.**

Example:
```javascript
class Employee {
    constructor(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    getFullName() {
        return `${this.firstName} ${this.lastName}`;
    }

    getInitials() {
        return this.firstName[0] + this.lastName[0];
    }
}

class Manager extends Employee {
    sendPerformanceReview() {
        console.log(`Sent performance review for current quarter`);
    }   
}
```

It is also possible to override methods in "child" classes.

[[super]]
[[prototypical inheritance]]