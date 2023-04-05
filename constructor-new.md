Constructor functions technically are regular functions. There are two conventions though:
1.  They are named with capital letter first.
2.  They should be executed only with `"new"` operator.

> We can use constructor functions to make multiple similar objects.

For instance:
```js
function User(name) {
	this.name = name;
	this.isAdmin = false;
} 

let user = new User("Jack");
alert(user.name); // Jack
alert(user.isAdmin); // false
```

When a function is executed with `new`, it does the following steps:
1.  A new empty object is created and assigned to `this`.
2.  The function body executes. Usually it modifies `this`, adds new properties to it.
3.  The value of `this` is returned.