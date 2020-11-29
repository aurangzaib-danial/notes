# Float
This property allows us to wrap elements around text without breaking the flow of the HTML document. It is just like newspapers, images are wrapped around text.

## Problem with float
Floating an element, makes its parent forget its height. The parent can only remember its height when their is a children which is cleared past the height of floated element. The **clear** property exists solely for this purpose.

The float property was widely used for complex layouts before the advent of flexbox and grid. The float had many problems and there used to be hacks to fix that. The floats were never supposed to be used for creating layouts.
