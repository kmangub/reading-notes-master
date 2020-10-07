# CSS Grid
Starting off, we have the grid code below:

```
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}
```

This will give us a 5 by 5 grid.

## Grid Column

Typing both `grid-column-start and grid-column-end` every time can get tiring. 

`grid-column: 2 / 4;` - 
will set the grid item to start on the 2nd vertical grid line and end on the 4th grid line.

## Grid Row
`grid-row-start: number` - moves the selector vertically. 


## Grid Area
If typing out both grid-column and grid-row is too much for you, there's yet another shorthand for that. `grid-area` accepts four values separated by slashes: `grid-row-start`, `grid-column-start`, `grid-row-end`, followed by `grid-column-end`.

## Order

By default, all grid items have an order of 0, but this can be set to any positive or negative value, similar to z-index. For example:

```
order: 1
```
## Grid Template Columns
We can set up the width to be wider than 20% and we can do that by inputting this:

```
 grid-template-columns: 50% 20% 20% 20% 20%
 ```

 Which means the first column will be wider.

## Repeat

Instead of using:
```
grid-template-columns: 20% 20% 20% 20% 20%;
``` 
we can use:

```
grid-template-columns: repeat(5, 20%);
```

## Units

The units can be in percentages, ems, px, and fr. Fr is fractionals and it allocates one share of the available space.

## Grid Template

Shorthand for both `grid-template-rows` and `grid-template-columns`.

For example, `grid-template: 50% 50% / 200px`; will create a grid with two rows that are 50% each, and one column that is 200 pixels wide.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)

 