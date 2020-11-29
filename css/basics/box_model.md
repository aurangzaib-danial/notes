# Box model
- In HTML, everything is a box.
- Some have width and height and some only width.
- Every box has border, padding and margin properties.

> There are two types of boxes in HTML, content-box and border-box

## Content box (All except IE)
- If a box follows content box rules  then **padding**, **border** values of the box add up to the actual width of the box.
- This is annoying in responsive design i.e. we have exact calculations for our layout and then later in the project if we want to add padding or a border to our box then we have to recalculate of box widths. 
- It has its pros as well.

## Border-box (Internet Explorer, Bootstrap default)
- Padding and border values are not added to the actual width instead they use up the width of the content. 
- The width for the content decreases but overall width of the box remains the same.

```css
* {
    box-sizing: border-box;
}
/* Support for older browsers for box-sizing property */
* {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```

<div style="text-align: center;">
  <img src="https://i.imgur.com/flaCRX1.png" alt="box models">
</div>


