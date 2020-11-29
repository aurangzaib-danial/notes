# Position
Position property allow us to position our elements on the web page, however we like

It accepts four values static, relative, absolute and fixed.

> Setting position property to any value other than static gives us access to top, left, right and bottom properties through which we can change the position of the element.

## Static
This is the default for every element. It does not apply any rule on an element.

## Relative
- This means element is positioned relative to its original position.
- When we make an element's position relative, we get properties like top, right, left and bottom.
- Setting an element's position relative does not remove its space from the flow of the web page.
- The space of the element is still occupied but changing its position using top etc. does not effect other elements like it does with margin.

## Absolute
- An absolute element is positioned relative to the window by default.
- It breaks out of the normal flow of the web page. It has no effect on other elements whatsoever.
- Setting its position coordinates as top: 0; left: 0; 0 means the edge, this will be by default edge of the window.

> To position an absolute element relative to its container then we have to set the parent element's position relative. By setting the position of the parent, we force the absolute element to position itself relative to its parent element.

## Fixed
- Remove elements from the flow of the web page. 
- Always relative to the window, cant change that. 
- This will be fixed at a place and will not move out of sight even if we use scroll to another section.

## z-index
If we have elements overlapping each other because of position property then we can use z-index and increase appearance priority of an element.


