## naming conventions

```
    2            +           2
/operand/ - /operator/ - /operand/
```

- `unary` operator has only one operand
- `binary` operator has two operands
- `ternary` operator has three operands. There is only one ternary operator: [conditional ternary operator](conditional-ternary-operator.md)

### list of all operators (precedence order)

| precedence | symbol            | explanation                                                                       |
| ---------- | ----------------- | --------------------------------------------------------------------------------- |
| 17         | ` ?. ...`         | [optional chaining](optional-chaining.md)                                         |
| &nbsp;     |                   |                                                                                   |
| 15         | `... ++`          | postfix [increment](increment.md)                                                 |
| 15         | `... --`          | postfix decrement                                                                 |
| &nbsp;     |                   |                                                                                   |
| 14         | `-`               | unary negation                                                                    |
| 14         | `+`               | unary plus see: [type-conversion](type-conversion.md)                             |
| 14         | `~`               | [bitwise NOT](bitwise-not)                                                        |
| 14         | `!`               | logical NOT                                                                       |
| 14         | `delete`          | delete given object property                                                      |
| 14         | `typeof`          | [typeof](typeof.md)                                                               |
| 14         | `void`            | void                                                                              |
| 14         | ++ ...            | prefix [increment](increment.md)                                                  |
| 14         | -- ...            | prefix decrement                                                                  |
| &nbsp;     |                   |                                                                                   |
| 13         | `**`              | [exponentiation](exponentiation.md)                                               |
| &nbsp;     |                   |                                                                                   |
| 12         | `*`               | multiplication                                                                    |
| 12         | `/`               | division                                                                          |
| 12         | `%`               | [division-remainder](division-remainder.md)                                       |
| &nbsp;     |                   |                                                                                   |
| 11         | `+`               | addition, [string-concatenation](string-concatenation.md)                         |
| 11         | `-`               | subtraction                                                                       |
| &nbsp      |                   |                                                                                   |
| 10         | `<<`              | [bitwise-left-shift](bitwise-left-shift)                                          |
| 10         | `>>`              | [bitwise-right-shift](bitwise-right-shift)                                        |
| 10         | `>>>`             | [bitwise-unsigned-right-shift](bitwise-unsigned-right-shift)                      |
| &nbsp;     |                   |                                                                                   |
| 9          | `<`               | less than                                                                         |
| 9          | `<=`              | less than or equal                                                                |
| 9          | `>`               | greater than                                                                      |
| 9          | `>=`              | greater than or equal                                                             |
| 9          | `instanceOf`      | returns `true` if the object on the left is an instance of the class on the right |
| 9          | `in`              | returns `true` if the value on the left is a key of the object on the right       |
| &nbsp;     |                   |                                                                                   |
| 8          | `==`              | equality                                                                          |
| 8          | `!=`              | inequality                                                                        |
| 8          | `===`             | strict equality                                                                   |
| 8          | `!==`             | strict inequality                                                                 |
| &nbsp;     |                   |                                                                                   |
| 7          | `&`               | [bitwise-and](bitwise-and)                                                        |
| 6          | `^`               | [bitwise-xor](bitwise-xor)                                                        |
| 5          | `ǀ`               | [bitwise-or](bitwise-or)                                                          |
| 4          | `&&`              | [logical AND](logical-and)                                                                       |
| &nbsp;     |                   |                                                                                   |
| 3          | `ǀǀ`              | [logical-or](logical-or.md)                                                       |
| 3          | `??`              | [nullish coalescing operator](nullish-coalescing.md)                              |
| &nbsp;     |                   |                                                                                   |
| 2          | `=`               | assignment                                                                        |
| 2          | `+=`              | assignment                                                                        |
| 2          | `-=`              | assignment                                                                        |
| 2          | `**=`             | assignment                                                                        |
| 2          | `*=`              | assignment                                                                        |
| 2          | `/=`              | assignment                                                                        |
| 2          | `%=`              | assignment                                                                        |
| 2          | `<<=`             | assignment                                                                        |
| 2          | `>>=`             | assignment                                                                        |
| 2          | `>>>=`            | assignment                                                                        |
| 2          | `&=`              | assignment                                                                        |
| 2          | `^=`              | assignment                                                                        |
| 2          | `|=`              | assignment                                                                        |
| 2          | `... ? ... : ...` | [conditional ternary operator](conditional-ternary-operator.md)                   |
| &nbsp;     |                   |                                                                                   |
| 1          | `,`               | [comma operator](comma-operator)                                                  |
