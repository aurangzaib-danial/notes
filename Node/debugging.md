

# Debugging
There are two ways to debug a node application i.e. chrome console and the shell.
The popular one is the 'chrome console'.

But I do not like chrome console. The reason is, I have to open up chrome everytime I want to debug which is really exhausting and slow.

I like shell debugging which is pretty straight forward and fast.

## Shell debugging
Every global evaluation is a break point by default.

```js
let name = 'Sunny'

function hello() {
  debugger // we can't access the name variable when we are in debug mode for keeping the debug mode tight and fast
}

hello();
```

```shell
$ node inspect index.js
```

1. First the program will stop at the 'let definition'
2. We should use 'c' for continuing to the next break point (debugger) instead of stopping at each line. (It won't go the debugger breakpoint first, so use 'c'. We can't do anything about that yet)
3. Use 'n' for next line but it's not very deep.
4. Use 's' for deep line by line breaks.
5. Use 'repl' for interactive with current code.

## Browser debugging
```shell
$ node inspect index.js
```
Open up chrome browser's dev tools and then open dedicated node dev tools for a console session.
