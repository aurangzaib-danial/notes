# Hoisting
It is all about bringing all the declaration of variables to the top of the scope so they can be used even before their declaration. This feature is for specific people and it was intentioned. I personally do not like hoisting and never do anyone else but this is part of the language, we need to understand it and keep it in mind so that we do not unintentionally allow hoisting.

## Variable hoisting
```js
console.log(name) //=> undefined, because only the declaration is hoisted
var name = 'Sunny'
console.log(name); //=> 'Sunny'
```
Above problem can be totally avoided by the usage of 'let' and 'const'. The compiler knows where they are declared but they cannot be used until they actually defined.

## Function hoisting
Normal function definition is always hoisted but declaring functions using variables are not hoisted.

```js
sayHello() //=> Hello World!

function sayHello() {
  'Hello World!'
}
//-------

sayHello() //=> Function not defined error

var sayHello = () => 'Hello World';
```

Hoisting is weird and we do not like it. Keeping above things in mind, will surely help me avoid errors and surprise.
