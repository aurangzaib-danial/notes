
# Code blocks

We can use code blocks to display code in our markdown.

We can display code in three ways.

1. in-line code
2. Code block.
3. Fenced code block.

```md
This is an example of in-line code. The ruby `class` is awesome.
Wrap the text with one back tick.

```

Simple code block just renders code without any syntax highlightning.

```md
    ```
      3.times do
        puts 'I love markdown'
      end
    ```
```

In fenced code blocks, we can specify the name of the language.

```md
    ```js
    console.log('This works!')
    ```
```

Fenced code blocks, show syntax highlightning and it works for various languages.
