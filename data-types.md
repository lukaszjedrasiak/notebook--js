JavaScript is an objective oriented language. It means, that you do not define global functions, which operate on different data types. Instead, you use different data types, which has defined methods.

I.e. If you want to sort an array you do not call function `sort(array)`, but call method `array.sort()`.

> [!info] js is dynamically typed language
> There are different data types in js, but variables are not bound to any of them. One variable may be a string and then store a number.

## list of data types

1. [numbers](numbers)
2. [BigInt](bigint)
3. [strings](strings)
4. [boolean](boolean)
5. [null](null)
6. [undefined](undefined)
7. [objects](objects)
8. [symbols](symbols)

You can check a type of operand (i.e. variable) using [typeof](typeof.md) operator. It returns a string with the type name.

```js
typeof 0 // "number"
typeof 10n // "bigint"
typeof true // "boolean"
typeof "foo" // "string"
```

> [!note]
> Primitives data types are **mutable** and objects are **immutable**.

---

Learn more about [type conversion](type-conversion.md) – changing one data type into another.

Learn more about [object to primitive conversion](object-to-primitive-conversion).