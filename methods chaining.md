```javascript
course.markAsCompleted().setGrade(18).requestCertificate();

class Course {
    constructor(name, isCompleted) {
        this.name = name;
        this.isCompleted = isCompleted;
    }

    markAsCompleted() {
        this.isCompleted = true;
        return this; // allows method chaining
    }

    setGrade(grade) {
        this.grade = grade;
        return this; // allows method chaining
    }

    requestCertificate() {
        this.askedForCertificate = true;
        return this; // allows method chaining
    }
}
```