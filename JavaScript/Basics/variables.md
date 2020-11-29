
# Variables
There are many types of variables in JS.

1. Global
2. VAR variable (bad scope)
3. let
4. const

Variables have a strange scope in JavaScript. Any variable that is defined ouside the function (it does not matter if the function is nested) is available inside the function.
**Keeping the above problem in mind, we must never define regular variables outside the context of a function**

All the variables defined inside the functions are protected and we can even form closures inside functions for protecting variables.

## Shadowy variables
Variables defined outside a function if we try to redefine them in our function then it will not have any effect on the outside ones. It can create a choas and it is best that we do not define any variable outside a function.

```js
let name = 'Sunny'

function greet() {
  let name = 'Ali'
  console.log(name) // Ali
}

greet()

console.log(name); // Sunny
```

## Global
These must never be used and if used then with utmost caution.

```js
name = 'Sunny'; // variable without any keyword like var becomes a global variable, no matter where they are defined
```

## VAR keyword
These have been the goto for defining tightly scoped variables. But there are a lot of problems with its scope as well and its use must be discourged over 'let' and 'const'

```js
var name = 'Sunny';
// Also
var name = 'Sunny';
name = 'Ali' // changes the value of previously defined 'name' variable and does not define a new global variable

```
- VAR has a function scope but do not have block scope

```js
var i = 5;
for (var i = 0; i < 10; i++) {
  // some statements
}
i // 10, i is redefined by the block

```

- VAR is hoisted to the top, i.e. it can be used even before the point of its declaration

**Above problems, are solved by _let_ and _const_**

## const
These make our variables, constant.

```js
const STUDENTS = ['Ali', 'Sunny']
STUDENTS = 'Ali' // cant reassign

```

## let
These are an improved version of var, do not allow hoisting and redefining it in a block does not alter the outside defined variable.

```js
let i = 5;
for (let i = 0; i < 10; i++) {
  // some statements
}
i // 5
```
