If you want to add additional parameter to child class you need to call new constructor. You can reference to the parent constructor as well but need to call it with `super` statement:

```javascript

//additional parameter 'department'

class Manager extends Employee {
    constructor(firstName, lastName, department) {
        super(firstName, lastName); // super must be called first
        this.department = department;
    }
```

The `super` keyword can be also used in methods overriding:
```javascript
    getFullName() {
        return super.getFullName() + " [manager]";
    }
```

