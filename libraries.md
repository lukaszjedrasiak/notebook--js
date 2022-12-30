### Lodash

#### debounce
To debounce a function is to make it wait a certain amount of time before running again. The goal of debouncing a function is to reduce overhead by preventing it from being called several times in succession.

```js
import {debounce} from 'lodash-es'

const button = document.querySelector("#my-button");

button.addEventListener("click", debounce(() => {
    console.log("Button clicked");
}, 150));
```

### date-fns

A collection of functions that make it easier to work with dates in JavaScript.

```bash
npm install date-fns
```

```javascript
import {format, addYears} from "date-fns";
```

### snackbar
A [snackbar](https://material.io/components/snackbars) is a UI pattern popularized by Material Design. There are several snackbar libraries. We'll be using the one called `snackbar`:

-   GitHub repo: https://github.com/andreruffert/snackbar
-   NPM: https://www.npmjs.com/package/snackbar