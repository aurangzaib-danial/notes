# Sticky Footer
When the height of the main content is small then a normal footer does not sticks to the bottom of the page and leaves a undesired empty space beneath it. To make a footer stick to the bottom, we have to use a technique.

## Steps
1. We have to wrap the entire content of the document except footer inside a **wrapper**.
2. We have to set the height of the wrapper to take up the full screen minus the height of the footer.

```css
.wrapper {
  min-height: calc(100vh - 90px); /* 90 is assumed height, later we will use dynamic height of footer */
}
/*
We are setting the height of the wrapper to 100% of viewport height minus the height of the footer.
*/
```

## vh sizing unit
- vh stands for viewport height.
- 1 vh is equal to 1% of entire viewport height.

## calc function
- This allows us to perform mathematically operations in css without having to do them manually. 
- It's also very smart as above we did `calc(100vh - 90px)`, it can convert the `100vh` into pixels and then minus `90` out of it, automatically.

## TODO
- Make the footer height dynamic.
