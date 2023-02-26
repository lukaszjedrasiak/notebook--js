If we have a method inside an object and we want to refer to the property of this object, we need to use the `this` keyword.

Example:
```js
let message = 'outside message';

let obj = {
    'message': 'inside message',
    
    sayInside () {
        console.log(this.message)
    },

	sayOutside () {
		console.log(message)
	}
}

obj.sayInside() // 'inside message'
obj.sayOutside() // 'outside message'
```

When you use an arrow function as an object method the above approach doesn't work. In that case the `this` keyword refers to the arrow function itself, not the calling object. It is recommended to avoid using arrow functions, when you need to use `this` keyword.