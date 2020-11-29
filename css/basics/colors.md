# Colors
In real-life complex colors are made by mixing the most basic ones which are red, green and blue, also called RGB.

In code, whenever we want a specific color, we have to tell computer the number of the colors which we want to mix so we can make a new color.

Two ways of specifying colors to computers.
**Hexadecimal numbers** and **RGB values**.

## Hexadecimal numbers are followed by a pound symbol #
```
#000000 => Black
#fff => white
```
There are three groups in a hexadecimal color number

'00', '00', '00'  

We can shorten the hexadecimal number if all the groups have a unique number

'00', '11', '00' can be shorten to '010'

'00', '1F', '00' cannot be shorten to '01F0' => this is wrong

## RGB values
These range from 0-255, takes three arguments, additional argument can handle opacity of the element.

```css
p {
  color: rgb(0, 0, 0)
  color: rgb(0,0,0, 0.5) /* make a little transparent */
}
```
