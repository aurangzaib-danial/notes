


# Testing Javascript
- Top testing frameworks are Mocha, Chai and Jasmine.
- The convention is to put all test files inside 'test' directory.
- We can test by running `$ mocha` but there is another convention in JS for running tests.

```shell
$ yarn add mocha expect
```

```js
// package.json
"scripts": {
  "test": "mocha"
}
```
Inside the scripts key, we add 'test' as well. In the test key's value, we can specify how our tests should run.

```shell
$ yarn test #=> run tests
# also mixes the mocha module to be used in the context of shell even if it's not installed globally
```

### Typical test file for mocha
```js
// test/test.js
const expect = require('expect')

describe('My first test suite', () => { 
  it('can pass the first test', () => {
    expect(1).toEqual(1)
  })

  it('can pass the second test', () => {
    expect(2).toBe(2)
  })
});
```

### Note on expect, assert
```js
const expect = require('expect')
const assert = require('assert');
```
expect and assert both are modules itself that can be used in any testing framework. These are not shipped with the framework itself and we have been given the choice of choosing between expect and assert style. Both of these methods have robust matchers for testing.

They way these can work in any environment is because every test has a pass or failing condtion and if expect or assert fail then they report it to the test.

