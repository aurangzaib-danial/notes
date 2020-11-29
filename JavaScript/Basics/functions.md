# Functions
- Functions are first class citizens in Javascript, what that means i.e. functions can be passed around just like an ordinary object
- Functions in JS do not raise an error if the required number of arguments are not passed or if excessive number of arguments are passed.

```js
function function_name(param_1, param_2) {
  // everything between the curly brackets is the body of the function
  // do magic here
};

function_name // this returns the function object itself that can used as an argument for other functions.

function_name(); // add parentheses executes the function
```
**It's important to use parentheses when defining a function even if it has no parameters.**

## Return value
- Functions that do not return anything, always return undefined.
- We have to use the **return** keyword for returning data to the program otherwise undefined will be returned.
- **return** keyword breaks the execution of the function

## Closures
Creating a closure is a technique in which a function remembers the scope in which it is defined.

```js
function outerFunction() {
  let name = 'Sunny'
  return function innerFunction() {
    return `Hello, ${name}!`
  }
}

console.log(outerFunction()()); //=> Hello, Sunny!
```

## Callbacks or Annoymous functions
A function that is passed as an argument to another function is called a callback. The purpose of this kind of functionality is pure abstraction. For example, if a function has always the same tear down but its body is changing.

```js
function myEach(array, callback) {
  for (let counter = 0; counter < array.length; counter += 1) {
    let element = array[counter]
    callback(element, counter) // callback can be different now but everything else will remain the same always
  }
}

/* We can run unique code in between whenever we use myEach.
All the repetition is abstracted away and we can just do the unique thing everytime 
This is the true magic of callbacks or annoymous functions
*/

myEach([1,2,3], (number) => {
  console.log(number)
})

myEach([1,2,3], (number) => {
  console.log(number + 2)
});
```



# Arrow functions
Arrow functions are shorter syntax version of normal functions. They have syntactic syntax that has been missing from JavaScript for ages.

- These were invented mainly for shortening anonymous functions syntax because annoymous functions are the best part of JS. 
- By default arrow functions have no name.

```js
() => {} // basic syntax but cant be used like this because it's annoymous

words.forEach((word, index) => {
  console.log(index, word)
});
```

- We can even assign arrow function to a variable, which actually becomes its name.

```js
const hello = () => {
  console.log('Hello')
}

hello.name; //=> hello
```
- Omit parentheses when parameter is only one

```js
const words = ['apple', 'mangoes']
words.forEach(word => {
  console.log(word)
});
```

- Arrow functions can be one-liner and the one-liner syntax also supports implicit returns ( thats the best part )

```js
const square = n => n * n
// Omit curly braces if the code can adjust on one line

// Consider following code for syntactic brevity
total = [1,2,3].reduce((sum, n) => (sum + n), 0); //=> 6
```

I really like the arrow functions and I have decided to use these for the sake of consistency.
