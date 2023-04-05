 Returns the part of the `string` between the start and end indexes, or to the end of the string.
 
``` javascript
string.substring(indexStart, [indexEnd]);
```

- `indexStart`: the position of the first character you'd like to include
- `indexEnd`: the position of the first character you'd like to ignore

This is almost the same as `slice`, but it allows `start` to be greater than `end` (in this case it simply swaps `start` and `end` values).

Negative values are not supported (mean `0`).