# Loops
1. for
2. while
3. do while

## for
- This is the most widely used loop. We can specify the counter variable, loop conditions and as well as increment the counter, all before body of the loop. - As long as the condition is true the loop will keep running.
- This is most useful when we know the limit for the counter.

```js
for (let counter = 0; counter < array.length; counter += 1) {
  // do magic
}
```
## while
This is mostly used when we do not know when the condition will become false

```js
let truthy = 1
while (truthy) {
  // do magic
}
```

## do while
Useful when we want to run the body of the loop at least once even if the condition is not met.

```js
do {
  // do magic
} while (0) // runs at least once even if the condition is false
```
