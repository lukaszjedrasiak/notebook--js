```
    2            +           2
/operand/ - /operator/ - /operand/
```

- `unary` operator has only one operand
- `binary` operator has two operands
- `ternary` operator has three operands. There is only one ternary operator (TO CHECK): [[ternary operator]]

## sum
``` javascript
2 + 2 // 4
```

## concatenation
``` javascript
console.log( "2" + "2" ) // "22"
console.log( '1' + 2 ); // "12"
console.log(2 + 2 + '1' ); // "41" and not "221"
console.log('1' + 2 + 2); // "122" and not "14"
```

The binary `+` is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.

## addition assignment
```js
+=
```
Addition assignment

## division reminder
```js
console.log(5 % 2); // 1
```

## exponentation
```js
console.log(2**8); //2^8 = 256
console.log( 4 ** (1/2) ); // 2 (power of 1/2 is the same as a square root)
```

## increment / decrement
- the _prefix_ form `++counter` increments `counter` and returns the new value
- the _postfix_ form `counter++` also increments `counter` but returns the _old_ value (prior to increment)

## bitwise operators
TO DO
-   AND ( `&` )
-   OR ( `|` )
-   XOR ( `^` )
-   NOT ( `~` )
-   LEFT SHIFT ( `<<` )
-   RIGHT SHIFT ( `>>` )
-   ZERO-FILL RIGHT SHIFT ( `>>>` )


## list of all

According to priority:

- `++`
- `--`
- `-`: change number sign
- `+` : conversion into number
- `~`
- `!`
- `delete`: delete given object property
- [[typeof]]
- `void`
- `**`
- `*`, `/`, `%`
- `+`, `-`
- `+`: string concantenation
- `<<`
- `>>`
- `>>>`
- `<`, `<=`, `>`, `>=`: number comparison
- `<`, `<=`, `>`, `>=`: alphabetical comparison
- `instanceOf`: returns `true` if the object on the left is an instance of the class on the right
- `in`: returns `true` if the value on the left is a key of the object on the right
- `==`
- `!=`
- `===`
- `!==`
- `&`
- `^`
- `|`
- `&&`
- `||`: returns first true value in the chain

```js
let max = maxWidth || preferences.maxWidth || 500
// it points to the first true value in chain. Unfortunately 0 is also false, so in this case the better choice will be `??` operator.
```

- `??`: returns first defined value in chain
- `?:`
- `=`
- `**=`, `*=`, `/=`, `%=`, `+=`, `-=`, `&=`, `^=`, `|=`, `<<=`, `>>=`, `>>>=`
- `,`: binary operator. It counts two values and returns the right

```js
for (let i=0,j=10; i < j; i++,j--) {
	console.log(i+j);
}
```