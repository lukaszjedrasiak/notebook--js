In JavaScript, the values below will be converted to `false` and everything else will be converted to `true`:
-   `false` (is already a boolean)
-   `null`
-   `undefined`
-   `0`
-   `NaN`
-   `""` (empty string)

### checking truthy/falsy value

```js
const truthyOrFalsy = value => value ? true : false;
```

## short-circuit evaluation

Instead of this snippet:
```js
let username = '';
let defaultName;
 
if (username) {
  defaultName = username;
} else {
  defaultName = 'Stranger';
}
```

you can use this one:
```js
let username = '';
let defaultName = username || 'Stranger';
```
