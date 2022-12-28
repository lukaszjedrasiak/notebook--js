## importing modules

```html
<!-- this will NOT work -->
<script>
    import {something} from "./file.js";
    // Syntax error
</script>
```

```html
<!-- this will work -->
<script type="module">
    import {something} from "./file.js";
    // works as expected
</script>
```

## popular bundlers
1.  Vite
2.  Parcel
3.  Webpack

`Vite` is the newest of these three and the best.  
`Parcel` is known for its ease of use as you can use it without having to configure it.  
`Webpack` is known for its complicated configuration, however, it's widely used in the JavaScript community.