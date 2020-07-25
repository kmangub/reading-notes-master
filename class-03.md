# Lists

There are three ways we can use lists with HTML:

1. Unordered list - created by using the `<ul>` element followed by a `<li>` element
2. Ordered list - created by using the `<ol>` element followed by a `<li>` element
3. Definition list - created by using the `<dl>` (definition list),`<dt>` (definition title), and the `<dd>` (definition) elements

> If you want to style the lists, refer to page *333-335* in the HTML book.

### Nested Lists

You can place lists inside of a list.

# Boxes

Boxes are created using either HTML or CSS by specifying a box width or height with percentages or pixel size. Pixel size is more accurate.

### Borders

**Borders** separates the edge of one box to another.

We can set the thickness of the border by choosing the selector and using the `border-width: ` and using `thin`, `medium`, or `thick`. Another way to specify thickness is by using `px`. We can also specify which side of the box by using:
* `border-top-width:`
* `border-bottom-width:` 
* `border-left-width:`
* `border-right-width:` 

We can style the borders utilizing the `border-style:` property. Below are ways you can style the box:

* `solid`
* `dotted`
* `dashed`
* `double`
* `groove`
* `ridge`
* `inset`
* `outset`

Border colors are chosen using the `border-color:` property.

### Margins

**Margins** create gaps between two borders.

* `margin-top:` 
* `margin-right:`
* `margin-bottom:`
* `margin-left:` 

> We can also us the shorthand `margin: px px px px`, where each values are top, right, bottom, and left respectively.

### Padding

**Padding** is the space between the border of the box and the content inside of it using the `padding` property.

# Decisions and Loops

Switch statements show a different message depending on what the level the user is at.

Loops check conditions repeat the code until the the condition is false.

#### Example:

``` 
for (var i = 0; i < 10; i++) {
    document.write(i);
}
```
The resulting iterations of i would be 0123456789 and the code stops running at 10.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)