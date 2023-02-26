By default, scripts are loaded and executed as soon as the HTML parser encounters them in the HTML file, the HTML parser waits to load the entire script before from proceeding to parse the rest of the page elements.

> The old convention was to put scripts right before the `</body>` tag to prevent the script from blocking the rest of the HTML content. Now, the convention is to put the script tag in the `<head>` element and to use the `defer` and `async` attributes.

## defer

Example:
```js
<script src="example.js" defer></script>
```

The _defer attribute_ specifies scripts should be executed after the HTML file is completely parsed. When the HTML parser encounters a `<script>` element with the `defer` attribute, it loads the script but defers the actual execution of the JavaScript until after it finishes parsing the rest of the elements in the HTML file.

When is `defer` useful?

When a script contains functionality that requires interaction with the DOM, the `defer` attribute is the way to go. This way, it ensures that the entire HTML file has been parsed before the script is executed.

## async

Example:
```js
<script src="example.js" async></script>
```

The `async` attribute loads and executes the script asynchronously with the rest of the webpage. This means that, similar to the `defer` attribute, the HTML parser will continue parsing the rest of the HTML as the script is downloaded in the background. However, with the `async` attribute, the script will not wait until the entire page is parsed: it will execute immediately after it has been downloaded. Here is an example of the `async` tag:

When is it useful?

`async` is useful for scripts that are independent of other scripts in order to function accordingly. Thus, if it does not matter exactly at which point the script file is executed, asynchronous loading is the most suitable option as it optimizes web page load time.