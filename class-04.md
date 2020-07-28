# Links
Links can take us to another page, another part of the page, open new web browsers, and start an email program with a recipient.

#### Example
```
<a href="http://www.imdb.com">IMDB</a>
```
Where `<a href="http://www.imdb.com">` is the opening tag with the website address inserted after the `=`, the human readable part where we want the user to click the link, and the closing tag `</a>`.

**URL** is Uniform Resource Locator.

###Linking to Other Pages on the Same Site
When we are directing the user to another page in the same site, we wouldn't need to put the whole url, but rather the **relative URL**, which are the files located on the smae folder.

#### Example

```
<ul>
  <li><a href="index.html">Home</a></li>
</ul>
```

### Directory Structures
Structures that are organized by folders relating to the page directories.

### Email Links

Same as links, except the contents inside of the quotations contain a `mailto:` followed by the email address we want to send it to. 

#### Example

```
<a href="mailto:karlomangubat92@gmail.com">Email me.</a>
```

### Open Links in a New Window

```
<a href="http://www.imdb.com" target="_blank">Internet Movie Database</a>
```
> It's good practice to let the user know that they are redirecting to another page. 

#Layout
We can position where we want each part of the elements go to create a very appealing page. The building blocks, or the block-level elements, house the smaller elements. We can control how the dimentions of the box or separate using borders, margin, and padding.

* Normal Flow - Block level elements appear in a new line.
* Relative Positioning - Pushes the element to the top, right, bottom, or left of where it would have been placed in normal flow.
* Absolute Positioning - The element will be taken out of normal flow and will move as the user scrolls up or down.
* Fixed Positioning - The element is placed in relation to the browser's window.  Think of the title of the page staying at the top as the user scrolls up or down.
* Floating Elements - The element gets placed to the left or right of the page and the word wraps around it using the `float:` property and indicating left or right. 

### Screen Sizes
Developers need to be cognizant on the different screen sizes the user might use, whether it's on their phone or a large monitor, and need to work with that.

The screen resolution are dots that show on the screen per inch. Designers usually keep around 960-1000 pixels wide.

# Functions, Methods, and Objects
Functions are methods that are grouped together to perform a task. Methods are similiar, except they are created inside of an object. Objects create models and they are made up of properties and methods.

### Declaring a Function
To declare a function, enter the keyword `function`, the name of the function followed by a `()`, and a `{}`. The functions are being run inside the curly brace.

The function is called using the name of the function, followed by `()`.

Parameters are set inside of the parenthasis.

# Pair Programming

Pair Programming is where two people are working on code together, but each person has a different role. Pair Programming consists of two roles: **Driver** and **Navigator**. 
* Driver - Writes code and handles the mechanics wuch as switching files, version control, and writing code.
* Navigator - Guides the driver and thinks about what to do next and converts algorithms to code. The Navigator can look up solutions on another screen, but doesn't write code.

There are six benefits to pair programming:

1. Greater Efficiency - Pair programming may be slow, but can produce high-quality code, which means less time debugging.
2. Engaged Collaboration - The focus is to get the code done and people are less likely to slack-off when they are relying on each other.
3. Learning from Fellow Students - We can learn new methods from each other, opening up new ideas to attack problems.
4. Social Skills - Navigating code can help with communication skills.
5. Job Interview Readiness - Pair programming can show-off your collaboration skills to the employer. Learning from others and working well with them is a **desired** skill.
6. Work Environment Readiness - Pair programming can equip us with skills that normal Computer Science Majors dont have after graduating college.
