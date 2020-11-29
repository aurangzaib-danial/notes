# Arrays
## Destructive functions
1. push
2. pop
3. unshift
4. shift
5. splice

Above functions are destructive by nature and always return an element instead of the array.

### splice
```js
let fruits = ['mangoes', 'apples', 'oranges', 'watermelons']
// specify where we want to start, how many elements we want to remove and also add elements at point of extraction
fruits.splice(1, 2, 'bananas', 'grapes'); 
```

## Non-destructive functions i.e. that do not change the original array
### slice
```js
// slice or extract elements from an array
fruits.slice(0, -1) // 0 => from, -1 => to
// 'to' is optional
fruits.slice(2) // ['oranges', 'watermelons']
;
```

## Indices are actually strings
```js
let names = ['sunny', 'ali', 'taha']
number['1'] // ali
number[1] // ali
;
```

## Spread operator
- Allows us to spread contents of an array
- Allows us to collect multiple arguments in an array for a function

### spreading elements
```js
let numbers = [1,2,3]
[...numbers, 4, 5] // [1,2,3,4,5]
;
```

### collecting elements
```js
function hello(...array) {
  console.log(array)
}

hello(1,2,3) // logs => [1,2,3]
```
