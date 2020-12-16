# Margins
- We have horizontal and vertical margins in CSS. 
- Horizontal margins do not collapse whereas vertical margins collapse.

## What is vertical margins collapsing?
When two elements are stacked vertically, one has a bottom margin and one has a top margin, their margins collapse and the margin that is the highest will be applied on the screen.

<img src="https://i.imgur.com/p5vbdSq.png" title="Elements stacked with margins visible in psuedo manner" width="400">

<img src="https://i.imgur.com/d1pXOh8.png" title="Collapsed margins" width="400">

To overcome this issue, we need to create some sort of element or space (padding, border) between the two stacked elements.
