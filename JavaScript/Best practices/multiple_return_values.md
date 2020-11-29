# Multiple return values
Returning values out of multiple if and else if branching is not pretty in JS.
The return can never be implicit, that's why it's not easy to read if we do it in the ruby way.

```js
function calculateAge(age) {
  if (age < 10) {
    return 'Kid'
  }
  else if (age < 15) {
    return 'Teenager'
  }
  else if (age > 18) {
    return 'adult'
  }
};

/* Using multiple times 'return' keyword does not feel right
We have only one way to fix this according to me
*/

// #=> Using functions for each conditional and then using comparison operators.
function calculateAge(age) {
  return kid(age) || teenager(age) || adult(age)
}
/* Above code has the added benefit of single responsibility principle. This way we can make a change to any component separately. */

```
Apart from above discussion, one liner arrow functions can implicitly return values. Multiple conditionals can be easily refactored by using arrow functions as well.
