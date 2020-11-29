
# Conditionals
Before talking about conditionals, we need to know the truthy and falsey values in JavaScript.

## Falsey values
1. 0 (zero)
2. '' (empty string)
3. false
4. NULL
5. undefined

All other values other than the above are **truthy values**

## List of conditionals
1. if, else if, else
2. ternary operator
3. switch statements

## if
start with 'if' keyword and wrap the conditions inside a bracket.

```js
const name = 'sunny'
if (name) {
  // do magic
} else if (condition)  {

} else {

}
```

### one liner if
```js
if (1) console.log('Hello'); // omit curly brackets
```

## ternary operator
```js
condition1 ? do_this : do_that;
```

## switch statement
```js
const color = 'red'

switch(color) {
  case 'red': 
    print_color(color)
    break
  case 'blue': 
    print_color(color)
    break
  case 1:
  console.log('Why did you enter 1?')
    break
  default: 
    console.log('We do not support this color')
}

function print_color(name) { console.log(`The color is ${name}.`) }
```
'break' is required for breaking a case statement but it is not required when the 'return' is used. 'return' completes the function and returns a value while 'break' just stops the execution where it is used.
