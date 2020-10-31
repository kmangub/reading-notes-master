# EJS

EJS is Embedded JavaScript. This means that we can create a template using only JavaScript. There are many use-case for EJS, which include:

- Injecting Values into views
- Loops and Arrays
- If / Else Statements
- Partials

To get started, we install the package by running the command `npm install ejs`. Then we use `let ejs = require('ejs')`. In addition, we create a `index.ejs` file to put all of our content. The syntax for using ejs is `<%><%>` like in the video, but other tags can be used. Here's a list that we can use:

- <% 'Scriptlet' tag, for control-flow, no output
- <%_ ‘Whitespace Slurping’ Scriptlet tag, strips all whitespace before it
- <%= Outputs the value into the template (HTML escaped)
- <%- Outputs the unescaped value into the template
- <%# Comment tag, no execution, no output
- <%% Outputs a literal '<%'
- %> Plain ending tag
- -%> Trim-mode ('newline slurp') tag, trims following newline
- _%> ‘Whitespace Slurping’ ending tag, removes all whitespace after it

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)