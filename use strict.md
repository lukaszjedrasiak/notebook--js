To fully enable all features of modern JavaScript, we should start scripts with "use strict".
```js
	'use strict';
	//...
```

The directive must be at the top of a script or at the beginning of a function body.

Without "use strict", everything still works, but some features behave in the old-fashioned, “compatible” way. We’d generally prefer the modern behavior.

Some modern features of the language (like classes that we’ll study in the future) enable strict mode implicitly.

## changes in strict mode

1. Calling a variable before declaring it will cause an error.