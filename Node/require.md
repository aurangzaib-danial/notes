


# require
Looks for modules inside 'node_modules'. Can also require our files.
Node modules have folders and each folder has an entry point of 'index.js'

```js
const express = require('express');
```
It's important to note that requiring a module does not return a constant. It is our job to store the returned function into a constant.


## require multiple modules convention
```js
// test-helper
const expect = require('expect')
const react = require('react')
const babel = require('babel-core')

module.exports = {
  expect: expect
  react: react
  babel: babel
}

// someFunction.test.js
helper = require('./test-helper')
helper.expect //....


// I prefer following for tests
global.expect = require('expect')
global.react = require('react')
global.babel = require('babel-core')

// someFunction.test.js
expect
react
babel;
```

## requiring files 
```js
// models/person.js
class Person {
  sayHello() {
    return 'Hey, Guys!'
  }
}

module.exports = Person

// test/person.test.js
require('test-helper')
const Person = require('../models/person')

describe('Person', () => {
  it('#sayHello greets', () => {
    let person = new Person
    expect(person.sayHello()).toEqual('Hey, Guys!')    
  })
})
```

