# CSS Notes

- CSS - Cascading Style Sheets
- RGB - Red Green Blue - ` background-color: rgb(214, 233, 176);`
- HSL - Hue Saturation Light
- Opacity - the transperency of objects range from 0 to one, where 0 is the most transparent and 1 is solid 
- Hex codes - hexidecimal code - #000000 or #000
- Layout - remember wireframe - how it arranges on the page
- Rule
```
p {
    color: red;
}
```
- Selector - select which part you want to style
- Property & value 
    - property is the aspects of the element you want to change.
    - values specify the settings you want to choose for the selected property
- Curly braces - `{}`

### Examples of Styles

- Width and height
- Borders
- Background color
- Position under browser window

- Typeface
- Size
- Color
- Italics, bold, uppercase,
- lowercase, small-caps

> With CSS, you can target different elements.

## Color

An example of changing texts inside of an element can be found below:

```
/* color name */
h1 {
color: DarkCyan;}
/* hex code */
h2 {
color: #ee3e80;}
/* rgb value */
p {
color: rgb(100,100,90);}
```
Color can be chosen in different ways. The first way is the RGB values and it's `rgb(x,x,x)', where x is a number from 0 to 255.

Another way color can be chosen is with hex codes. For example `#66cdaa` is red 102.

Finally, another way to choose color is by simply entering the names of the color. There are exactly 147 colors supported by browsers.

### Contrast

Contrast is very important when there's a lot of reading involved in your web pages. Traditionally, a black background with white texts is easier to read. Dark gray with white texts works as well.

### CSS3

CSS3 introduces the use of opacity, where it changes the transparency of bojects overlapping. CSS3 factors in HUE, Saturation, and lightness.