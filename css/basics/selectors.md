# Selectors
## Info on Nested Elements
- An element can have direct children
- Children elements inherit the properties of parent element
- An element can have siblings
- Siblings do not inherit from one another but can be helpful in CSS selectors

```html
<section> <!-- the parent element -->
    <p></p> <!-- the first sibling element/the first child-->
    <p></p> <!-- the second sibling element/the second child -->
</section>
```

## Important Information about id and class
- Must begin with A-Z or a-z
- We can use A-Z, a-z, 0-9, hyphen(-), underscore( _ ) afterwards
- one ID can only be used for one element
- A class can be used for multiple elements
- An element can have multiple classes

## Compound Selector
- Select multiple elements in one go
- We can use multiple selectors and give styling to all them at once

```css
h1, h2, p { color: blue; }

nav a, article#some_article a {
    color: black;
}
```

## Descendent Selector
Select all elements which are descendant of an element, by descendant mean nested and also deeply nested.

```css
article p { color: red; }
```

## Immediate children selector
Selects children at the first level of nesting, child which is the same element but nested more than first level will not be selected.

```html
<style type="text/css">
  article > p {
    color: blue;
  }  
</style>

<article>
    <p>hello world </p> <!-- will be selected -->
    <aside>
        <p>Bye world</p> <!-- will not be selected because nested more than first level -->
    </aside>
</article>
```

## Adjacent Sibling Selector
Selects only one element that comes directly after an element ( only if the element is at the same level of nesting as the element ) .

```css
h1 + p {
    color: blue;
}
```
**p** element has to come exactly after the **h1** otherwise if an element is before **p** then this selector will have no effect.

## General Sibling Selector
Selects all the specified elements that come after an element ( only if the elements are at the same level of nesting as the element )

```css
h1 ~ p { color: blue }
```
All the **p** elements which come after **h1** will be selected.

## Attribute Selector
Select elements based on their attribute values and we can also select based on attribute name.

```css
input[type="text"] { width: 400px; }
```
Only select the inpouts which have type as text.

## Pseudo Class Selectors
Select elements depending upon their states. Also, select children etc.

```css
a:hover {
    color: orange;
}

a:visited {
    color: red;
}

a:active {
    color: black;
}

p:first-child {
  /* all paragraphs that are first child of any element */
}

div :last-child {
  /* any last element of div */
}

div p:first-child {
  /* Selects the first p element inside the div */
}
```
