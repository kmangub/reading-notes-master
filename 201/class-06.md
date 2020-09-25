# Object Literals

- Objects - Group of variables and functions that model similarly what you would see in the real world.
- Property - Variables that pertain to the object.
- Method - Funtions that are part of an object.
- Key - Name and value. Keys can be strings, numbers, booleans, arrays, or another object.

To create an object named `hotel`:

1. Input `var hotel = {`
2. List out keys stating with `name: 'Quay',` separating with commas. Press enter twice.
3. Create a method by writing out the function name and what its doing. So, 
``` 
checkAvailability: function() {
  return this.rooms - this.booked;
}
```
4. Close out the object with `}`

To access objects, there are two ways:
1. Using dot notation
2. Square brackets

To access objects using **dot notation**:

1. Use the name of the object, followed by a period, and then the key you want to access.
2. Use the name again and call out the method after the period. Don't forget the '`()`'.

To access using square brackets:

1. Call out the object and open square brackets.
2. Insert keys you want to access inside square brackets.

# Document, Object, Model (DOM)

### DOM Queries

`getElementId('one');` grabs the element with id attribute of `one`.

`var itemOne = getElementById('one')`

To access, it's `itemOne` followed by a period.

### Methods That Select Individual Elements
`getElementById()` and `querySelector()` can search the documents and return elements.

`document.getElementById('one')` returns the element node with id attribute of '`one`'.

**Nodelists** is a collection of element nodes. Nodelists look like arrays, but are a type of object called a **collection**.

### Selecting an Element from a Nodelist

Item Method:
```
var elements = document.getElementsByClassName('hot')
if (elements.length >= 1) {
  var firstItem = elements.item(0);
}
```

Array Syntax:
```
var elements = document.getElementsByClassName('hot')
if (elements.length >= 1) {
  var firstItem = elements[0];
}
```

> The only difference is at the end with calling the elements.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)