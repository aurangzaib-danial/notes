# == vs ===
When comparing two values, it is best to use '===' because '==' will try to coerce values for comparison.

```js
number_string = '1'
number_string == 1 //=> true

number_string === 1 //=> false
```
