# Forms

We use forms to gain information from a user such as their preferred username, the choices they make, or a password.  Forms controls include the following:

- Check boxes
- Drop-dowm boxes
- Submit buttons
- Uploading documents

To use forms, we use the `<form>` element. Inside the form element, we need an action attribute. Forms can either use the methods **get** or **post**.

The `<input>` element creates the form controls.

- `type="text"` - creates a single line text input.
- `type="password"` - Hides the characters in the text box.
- `type="radio"` - lets the user make a choice from a series of options
- `type="checkbox"` - lets the user choose one or more options
- `type="file"` - creates a text box with a browse button where the user chooses a file to upload
- `type="submit` - send a form to the server
- `type="image"` - uses an image instead of a standard submit button
- `type="hidden"` - hides the form controls
- `type="date"` - inputs dates

The `<select>` element creates a drop down list.

The `<option>` element specifies the options that the user selects from.

The `<label>` element makes the form more accessible to vision-impaired users.

The `<fieldset>` element is used for longer forms.

Form validation makes informs the user that they filled out the form incorrectly.

# Lists, Tables, and Forms

We can use CSS properties to change the appearances of lists, tables, and forms usind the `list-style-type` property.

### Unordered Lists

To change the appearance of the bullet points for lists, we can use `disc`, `circle`, or `square`. We can also specify to not use one using `none`.

### Ordered Lists

- `decimal` - 1 2 3
- `decimal-leading-zero` - 01 02 03
- `lower-alpha` - a b c
- `upper-alpha` - A B C
- `lower-roman` - i. ii. iii.
- `upper-roman` - I II III

### Images for Bullets

We can use a specific image to use as bullets with css properties. For example:

```
ul {
  list-style-image: url("images/star.png");
}
li {
  margin: 10px 0px 0px 0px;
}
```
The `outside` property put the bullet points outside while `inside` property moves it inside. 

### Tables

We can show or hide the cells using the `empty-cells:` and indicating with `show` or `hide` afterwards.

Border spacing allows us to control the distance between each cell and this is achieved by using `border-spacing:` followed by the pixel size.

# Events

Events are used to tell the browser that something just happened and it responds accordingly. Events can be things like double-clicking an area on the webpage, or typing a key on the keyboard.

When hovering or clicking on a link, we are also clicking the elements that live inside of it. For **Event Bubbling**, the event starts at a specific node and it flows outward. For **Event Capturing**, the event flows inwards to a specific node. Flow matters when event handlers are on an element and one of its ancestor or descendant elements. 

Events occur where the cursor was positioned using x and y positioning. 

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)

