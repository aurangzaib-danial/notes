# Low level Javascript
By low level, I mean rendering graphics in the browser or registering a click event on a button.

```js
$("button").click(function(){
  alert("This button was just clicked")
});
```
## Above code registers a click event on a button element.
- How it registers it?
- How does it tell the browser that whenever this button is clicked run the underlying code?
All of this low level functionality is already handled by the language for us and all we have to do is use it for common good.

## Also graphics rendering in the browser
We use CSS to explain to the browser what kind of layout and styles we want.
The low level functionality of how these graphics are actually rendered is handled by the browser and we do not need to worry about it. We just have to use it and make programs.
