# Reading 01: Introductory HTML and JavaScript
 ### HTML
Hyper Text Mark-up Language (HTML) are text documents that create the structure of the web page using tags, which can be identified as angle brackets `<>`. 

There is an opening tag and a closing tag. 

Attributes tells more information about the contents of the element.

```
<p lang="en-us">Paragraph in English</p>
```
Where `lang` is the attribute name and `en-us` is the attribute value. 
### Common HTML Tags

* `<html></html>` - Always start with this to create the page.
* `<head></head>` - Contains information about the page.
* `<title></title>` - Contains the title of the page.
* `<h1></h1>`- Heading. The number indicates how big the heading is from largest to smallest, with 6 being the smallest. 
* `<p></p>` - Paragraph.

### Extra Markup

* `<!DOCTYPE html>` - lets the browser know which version of HTML the page is using

* `<!-- Insert comment here-->` - Use this to insert an inline comment. Not visible when rendering on the webpage.

* `<p id="pullquote"></p>` - This assigns an ID to the element. The ID in this case is `pullquote`.

* `<p class="important"></p>` - This assigns a class attribute.

* `<div></div>` - groups a set of elements together in one box.

### HTML5 Layout

* `<header></header>` - Displays on the top of the page.
* `<footer></footer>` - Displays on the bottom of the page.
* `<nav></nav>` - Contain links to navigate though the website. 
* `<article></article>` - Contain information inside a section.

> When using older browsers, include lines of CSS.

### Process & Design

When creating a website, it is important to know who your audience is. Once that has been established, you can create a **wireframe**, which is a blueprint of your website. Creating wireframes ensure you have everything you need to employ your website. 

**Visual Hierarchy** helps the user find exactly what they are looking for in the website. They often skim through websites to achieve their goal.

### The ABC of Programming

A script is a step by step instructions of what you want your webpage to do. It can be broken down to many different tasks. It helps if you create a flowchart. 

* `<script></script>` - When linking JavaScript from an HTML web page.

Below is an example of JavaScript:
```
document.write('Good afternoon!');
```
Where `document` is the object, `write('Good afternoon!')` is the method, and `'Good afternoon!'` are the parameters.