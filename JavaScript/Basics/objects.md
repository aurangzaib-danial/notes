# Objects
Objects in JavaScript can be created on-the-go or using a class. Objects that are created without a class can be used as a dictionary.

## Syntax
```js
let object = {} // literal syntax

// Creating key/value pairs
let studentsCount = { classOne: 10, classTwo: 20, classThree: 15}

// Accessing
studentsCount.classOne //=> 10

// Accessing using a variable
let className = 'classOne'
studentsCount[classOne] //=> 10

// Setting key using a variable
{[className]: 10}

//  Delete a key
delete studentsCount.classOne
// OR
delete studentsCount['classOne']
```

## Object.assign({}, object1, object2, ...)
- This method allows us to create new objects by copying keys from other objects. 
- This is the best way to avoid destructive changes on objects.

```js
let oldObject = {breakfast: 'eggs', lunch: 'meat'}

let newObject = Object.assign({dinner: 'salad'}, oldObject, { breakfast: 'milk'})
// Keys are overwritten from left to right
```
