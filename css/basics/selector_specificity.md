# Selector Specificity
- It's all about which css declaration would get precendence.
- When we are working with CSS libraries, those libraries define some css selectors by default.
- We have to overwrite it sometimes. 

## Specificity table
- The selectors we use for a declaration, each selector has a value in specificity table. 
- This specificity table is used by all browsers to find out which selectors for a specific element has the highest specificity value or precedence.

<div style="text-align: center;">
  <img src="https://i.imgur.com/re6nr91.png" alt="specificity table">
</div>

| Style attribute | ID | Class + Psuedo-class | Elements (div, a etc.) |
| --- | --- | --- | --- |
| 1,0,0,0 | 0,1,0,0 | 0,0,1,0 | 0,0,0,1 |

## Important notes
- If the same selectors are used twice for an element then the one which comes later in the css file will receive precedence.
- If some selectors for an element have higher specificity value then even if some selectors are define later in the css file, if they have specificity lower than the previous selectors then the selectors which have higher precedence will be chosen by the browser.
- By being specific we are protecting ourselves in a way that if we forget and overwrite an element styling later in our code then we will know, why our styling did not work because the previous style was specific, now if we want overwrite then we have to be more specific.

- Style attribute has the highest specifity value
- For each ID in the selector add 0,1,0,0
- For each class and psuedo class attribute add 0,0,1,0
- For element add 0,0,0,1

## Example
```css
ul li:first-child p { color: red; } /* 0, 0, 1, 3 */ 
ul#my_list li:first-child p { color: blue; } /* 0,1,1,3 */
/* Second method has the highest precedence and will overwrite first method */
```

## `!important` is an automatic win
- We cannot use !important property in our css, it's only for edge cases and should not be used for the most time.
- Using important even overwrites in-line styling.

```css
p {
    color: red !important;
}
```

## Increasing specificity on a single selector
```css
h2#myHeading.black.white { color: yellow; } /* element name can only come at start */
```

## Semantic CSS by being Specific
```css
div#myHeader { display: block }
#myHeader { display: block }
/* First method clearly tell us what kind of element #myHeader is */
```

[Smashing Magazine - CSS Specificy](http://www.smashingmagazine.com/2007/07/27/css-specificity-things-you-should-know/)

[CSS Tricks - CSS Specificity](http://css-tricks.com/specifics-on-css-specificity/)

[Specificity Calculate](https://specificity.keegan.st/) 
