- Every JavaScript file is called a **Module** (or **ES Module**).
- Every JavaScript file (every module) is separate from the outside world. Every variable you define in a file with `let` or `const` is only available in that file, and not in the other files. The same applies to functions & classes.
- BUT – declarations in files that are not modules are available in the whole document and do not need to be imported!!!
- You can make variables/functions/classes available to other files by **export**ing them from the current file and then **import**ing them from another module/file.
- The path must start with `./` when importing from a local file. Make sure you've got the correct path (if there are folders).

## summary

```js
// Importing default exported module
import BitSet from './bitset.js'
```

```js
// importing multiple symbols from one module
import {mean, stddev} from './stats.js'
```

```js
// importing every symbol from one module
import * as stats from './stats.js'

// imported symbols can be calle as `stats.mean()` and `stats.statdev()`
```

```js
// importing defauld symbol and other named symbols from one module
import Histogram, {mean, stddev} from './stats.js'
```

```js
// importing a symbol that is not exported
import './analitycs.js'

// this symbol is invoked only once after first import
```

```js
// importing with name change
import {render as renderImage} from './image.js'
```

## export

Exporting single class / function / etc. from module

```js
//helper.js
export class Helper {
	//...
}
```

Exporting multiple classes / functions from module

```js

class Helper {
	//...
}

const sth() {
	//...
}

export {Helper, sth}

```

## import

```js
//index.js
import {Helper} from "./helpers.js";

new Helper(); // works as expected
```

```html
<!-- embedding those scripts without bundler like webpack/parcel -->
<script type="module" src="index.js"></script>
```

> `import` syntax can be used only inside a `module` (whatever it means), so you have to add an attribute `type` to `script` tag within the HTML file.

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

[modules import-export example](modules-import-export-example)
[importing default values](exporting-importing-default-values.md)

[[module bundlers]]
[[package managers]]

### Importing from library
[[libraries]]

Install module
```bash
npm install lodash-es
```

Import all library:
```javascript
// 👎 NOT recommended
import _ from "lodash-es";
```

Import selected functions:
```javascript
// 👍 recommended
import {debounce} from "lodash-es";
```

### dynamic import

IMPORTANT! The importet modules are visible and can be used only inside the `import` function.

```javascript
import("lodash-es").then(module => {
    const debounce = module.default; // because debounce is a default export
    // use debounce inside this function...
});

import("./helpers.js").then(module => {
    const Helpers = module.default; // because Helpers is a default export
    const getDate = module.getDate; // because getDate is a named export
    // use Helpers and getDate inside this function...
});
```

With async/await
```javascript
const button = document.querySelector("#button");

button.addEventListener("click", async () => {
    const module = await import("chat-library");
    module.init();
});
```

With destructuring
```javascript
const button = document.querySelector("#button");

button.addEventListener("click", async () => {
    const {init} = await import("chat-library");
    init();
});
```