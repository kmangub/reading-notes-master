  # Flexbox and Templating

  The flexbox layout is a way to organize items on the webpage by using the available space and altering the item's width and height.   

  ## Properties for the parent (flex container)

  ### **display** - Defines a flex container depending on the given value for its direct children.

  ```
  .container {
  display: flex; /* or inline-flex */
  }
  ```
  ### **flex-direction**
  Establishes the main-axis and defines the direction in the flex container. It lays out in either the horizontal rows or vertical columns.

  ```
  .container {
  flex-direction: row | row-reverse | column | column-reverse;
  }
  ```

- *row (default)*: left to right in ltr; right to left in rtl
- *row-reverse*: right to left in ltr; left to right in rtl
- *column*: same as row but top to bottom
- *column-reverse*: same as row-reverse but bottom to top

### **flex-wrap** 
Wrap as needed.

```
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

- *nowrap* (default): all flex items will be on one line
- *wrap*: flex items will wrap onto multiple lines, from top to bottom.
- *wrap-reverse*: flex items will wrap onto multiple lines from bottom to top.

### **flex-flow**
Shorthand for the flex direction and the flex wrap properties. 

```
.container {
  flex-flow: column wrap;
}
```
### **justify-content**
Defines the alignment across the main axis and helps distribute all of the remaining space.

```
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe;
}
```

- *flex-start (default)*: items are packed toward the start of the flex-direction.
- *flex-end*: items are packed toward the end of the flex-direction.
- *start*: items are packed toward the start of the writing-mode direction.
- *end*: items are packed toward the end of the writing-mode direction.
- *left*: items are packed toward left edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
- *right*: items are packed toward right edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
- *center*: items are centered along the line
- *space-between*: items are evenly distributed in the line; first item is on the start line, last item on the end line
- *space-around*: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
- *space-evenly*: items are distributed so that the spacing between any two items (and the space to the edges) is equal.

### align-items
This is how the flex items are laid out.

```
.container {
  align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe;
}
```

- *stretch (default)*: stretch to fill the container (still respect min-width/max-width)
- *flex-start / start / self-start*: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the flex-direction rules or the writing-mode rules.
- *flex-end / end / self-end*: items are placed at the end of the cross axis. The difference again is subtle and is about respecting flex-direction rules vs. writing-mode rules.
- *center*: items are centered in the cross-axis
- *baseline*: items are aligned such as their baselines align

### **align-content**
Aligns a flex container's lines when there is extra space in the cross-axis.

```
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;
}
```
- *normal (default)*: items are packed in their default position as if no value was set.
- *flex-start / start*: items packed to the start of the container. The (more supported) flex-start honors the flex-direction while start honors the writing-mode direction.
- *flex-end / end*: items packed to the end of the container. The (more support) flex-end honors the flex-direction while end honors the writing-mode direction.
- *center*: items centered in the container
- *space-between*: items evenly distributed; the first line is at the start of the container while the last one is at the end
- *space-around*: items evenly distributed with equal space around each line
- *space-evenly*: items are evenly distributed with equal space around them
- *stretch*: lines stretch to take up the remaining space

## Properties for the Children (flex items)

### **order**
Controls the order that they appear in the flex container.

```
.item {
  order: 5; /* default is 0 */
}
```
### ** flex-grow
Indicates the amount of space in the container should take up.

```
.item {
  flex-grow: 4; /* default 0 */
}
```
### **flex-shrink
This causes the flex item to shrink.

```
.item {
  flex-shrink: 3; /* default 1 */
}
```

### **flex-basis**
This defines the default size of an element before the remaining space is distributed.

```
.item {
  flex-basis:  | auto; /* default auto */
}
```
### **flex**
This is the shorthand for **flex-grow**, **flex-shrink** and **flex-basis** combined.

```
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

### **align-self**
This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

```
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)
