# Basics of HTML, CSS & JS

### Text

* `<sup></sup>` - superscript, or exponents in mathematical formulas

* `<sub></sub>` - subscript, or footnotes in chemistry formulas

* `<br />` - creates breaks in the middle of the paragraph. 

* `<hr />` - horizontal rule.

* `<strong></strong>` - Strong emphasis, or by default, bold

* `<em></em>` - Emphasis, or by default, italic

* `<blockquote></blockquote>` - Indents the quote. Usually includes the source in the code.

* `<q></q>` - Inserts quotation marks. 

* `<abbr></abbr>` - Abbreviations.

* `<cite></cite>` - Citations.

* `<dfn></dfn>` - Definition.

**Whitespace collapsing** is where the browser ignores the spaces in between words that are greater than 1 or in new lines.

### CSS

Cascading Style Sheets (CSS) is how the web page appears to the user. It is more on the presentation of your website and the rules can be applied from another document.

CSS code consists of two parts: **Selector** and **Declaration**.

Selector is choosing what you want to be styled. Examples include `<p>`, `<header>`, and `<img>`.

Declaration is how you want the selector to be styled. Examples include `color:`, `background-color:`, and `width`.

You can include CSS within an html by using `<style></style>` and follow the format of CSS inside the element.

There are different types of selectors and can be found below:

* `* {}` - Universal selector that applies to all elements.

* `.example` - Class selector that applies to all class.

* `#example` - ID selector targets elements with the same ID.

> If the two selectors are identical, the latter of the two will take precedence. This is called the **Last Rule**.
