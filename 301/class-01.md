# SMACSS, Responsive Web Design, and Float

**Responsive** Web Design is where we would build sites that is compatible with every device. **Adaptive** change is where the website can be easily changed depending on the situation. **Mobile** is building a separate page on a different domain for mobile users.

### Relative Viewport Lengths

- `vw` - Viewports width
- `vh` - Viewports height
- `vmin` - Minimum of the viewport’s height and width
- `vmax` - Maximum of the viewport’s height and width

The use of fixed measurements are unpopular because the layouts of the device have a variety of different lengths and widths. 

### Flexible Grids

Using the formula `target / context = result`, we can create a grid with fixed units of length and changes them to relative units.

### Media

Media Queries are specifically for media. It is used to target styles for browser and device combinations. To use media queries, we use `@media` or the `@import` rule. 

There are three **Logical Operators** that we use to help us build powerful expressions and they are `and`, `not`, and `only`.

**Media Features** target attributes within the query expressions. 

**Orientation** media feature determines if the media is in portrait or landscape orientation. 

**Aspect Ratio** tells us the width and height pixel ratio of the rendering area or the ouput device.

# Float

We use the float property to place images on to the webpage, followed by the text, or vice versa. Below is an example taken from https://css-tricks.com/all-about-floats/ by Chris Coyier:

```
#sidebar {
  float: right;			
}
```

the `clear` property is used to move the element past the float and will look neater. A sample code is written below:

```
#footer {
  clear: both;			
}
```

### The Empty div Method
This has no purpose other than presentation; similar to a `<br>`.

```
 <div style="clear: both;"></div>
 ```

 ### Overflow Method
This expands the element and clearing it for the following elements.

### Easy Clearing Method

```
.clearfix:after { 
   content: "."; 
   visibility: hidden; 
   display: block; 
   height: 0; 
   clear: both;
}
```

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)