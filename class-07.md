# Tables
We use tables to organize data to a grid format in HTML.

`<table></table>` is the opening/closing tags for tables. Inside the element, we would use the `<tr></tr>`, which stands for table row. Inside of that, we would add `<td></td>`, which stands for table data.

In place of the `<td>` element, we could use `<th></th>`, which stands for table heading.

We can span the tables cells if we need them to stretch out. To do that, we need can use `<td colspan="2">` and then close it out with a `<td>`. This will stretch out the column **horizontally 2** spaces. 

Similarly, we can span rows too using the smae format. To do that, it's just `<td rowspan="3">` and then closed out with a `<td>`. This will strecth out the row **vertically 3** spaces. 

`<thead>` - Headings of the table.

`<tbody>` - The body of the table. This area could represent data.

`<tfoot>` - The footer of the table. This could represent the total of something.

We can adjust the table with following code:

```
<table width="400" cellpadding="10" cellspacing="5">
```
Where width is the how wide the table is, cell padding is the space from the edge of the cell to the content, and the cell spacing is the the spaces in between the cells. 

We can also use the the following code to create a border and a background color:

```
<table border="2" bgcolor="#efefef">
```
Which will give us a table border of two and a background color of grey.


# Functions, Methods, and Objects

`var hotel = new Object();` will allow us to create a blank object and add properties and methods to that object.

You can update using dot notation or bracket notation. To update, we use any method followed by a value in quotation marks. We can remove a property by using the `delete` keyword followed by the object and property.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)

