This will not work:
```js
(  
  <h1>  
    {  
      if (purchase.complete) {  
        'Thank you for placing an order!'  
      }  
    }  
  </h1>  
)
```

This will work:
```js
const ordered = false;
const heading = (<h1></h1>)

if (ordered === true) {
	heading = (<h1>Thank you for placing an order</h1>)
} else {
	heading = (<h1>Try again</h1>)
}
```

This will work too
```js
const heading = (
	<h1>
		{ordered ? 'Thank you' : 'Try again'}
	</h1>
)
```

## && operator

```js
const tasty = (
	<ul>
		<li>Applesauce</li>
		{ !baby && <li>Pizza</li> }
		{ age > 15 && <li>Brussels Sprouts</li> } 
		{ age > 20 && <li>Oysters</li> }
		{ age > 25 && <li>Grappa</li> }
	</ul>);
```

If the expression on the left of the `&&` evaluates as true, then the JSX on the right of the `&&` will be rendered. If the first expression is false, however, then the JSX to the right of the `&&` will be ignored and not rendered.