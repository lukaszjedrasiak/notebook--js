- Every JavaScript file is called a **Module** (or **ES Module**).
- Every JavaScript file (every module) is separate from the outside world. Every variable you define in a file with `let` or `const` is only available in that file, and not in the other files. The same applies to functions & classes.
- You can make variables/functions/classes available to other files by **export**ing them from the current file and then **import**ing them from another module/file.
- The path must start with `./` when importing from a local file. Make sure you've got the correct path (if there are folders).

## import / export
```js
//helper.js
export class Helper {
	//...
}
```

```js
//index.js
import {Helper} from "./helpers.js";

new Helper(); // works as expected
```

```html
<!-- embedding those scripts without bundler like webpack/parcel -->
<script type="module" src="index.js"></script>
```

### Renaming imported module
```javascript
import {getDate as getDateHelper} from "./date-helpers.js";
```

### Sample usage
```js
export class NumericHelper {
    constructor(number) {
        this.number = number
    }

    isEven() {
        return this.number % 2 === 0;
    }

    isOdd() {
        return this.number % 2 === 1;
    }
}
```

```js
import {NumericHelper} from "./numeric-helper.js"
const isEvenNumber = number => {
    // Use NumericHelper's isEven method to check if it's even
    return new NumericHelper(number).isEven();
}
```

### Importing from library
To be done later