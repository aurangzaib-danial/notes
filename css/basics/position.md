# Position
Position property allows to place elements anywhere on the webpage.

It accepts four values static, relative, absolute and fixed.

> Setting position property to any value other than static gives us access to top, left, right and bottom properties through which we can change the position of the element.

## Static
This is the default for every element. It does not apply any rule on an element.

## Absolute
- Absolute positioned element is taken out of the normal flow of web page and doee not affect others.
- It is positioned always in relation to the parent container because it has to keep something in perpective for positioning itself. It is always positioned relative to the closest parent who has relative positioning. Further, property like width is also depended on the parent container.

## Relative
- This means element is positioned relative to its original position from where top, right, left and bottom properties will be applied.
- Setting an element's position relative does not remove its space from the flow of the web page.
- The space of the element is still occupied but changing its position using top etc. does not effect other elements like it does with margin.

## Fixed
- Remove elements from the flow of the web page. 
- Always relative to the window, cant change that. 
- This will be fixed at a place and will not move out of sight even if we use scroll to another section.
- The width of the element will be only as much as the content. We have to increase it or set it full by ourself.

## z-index
- If we have elements overlapping each other because of position property then we can use z-index and increase appearance priority of an element.
- Default z-index of positioned elements is zero.
- Only works for elements with positioning set to absolute, fixed or relative.
- There are also stacking contexts, in which a element having higher z-index is under an element of lower z-index. Find more about stacking context [here][stacking context].

[stacking context]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context
