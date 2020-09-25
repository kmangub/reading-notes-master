# Images

Add images to make your website more lively. 

To add an image:

1. Open an `<img src="image-url"` and insert the url of the image after in quotation marks. Image URL end with a `JPEG`, `GIF`, or `PNG`.
2. Add a description of the image in the quotation marks `alt="image description"`
3. Provide additional information in the quotation marks `title=""`. Some browsers will display this when hovering the mouse over the image.
4. Close with ` />`

Altogether, it should look like this:

`<img src="image-url" alt="image description" title="additional information" />`

> Alt and title are strings.

### Height and Width

We can add height and width right before the closing the image tag. So, `<img src="image-url" alt="image description" title="additional information" width="600" height="450"/>`.

### Aligning Images

To align images, use the `align="left"` or the `align="right"` attribute.

### Figures 

We use `<figure></figure>` to show an image and the caption of that image. It contains the `<img>` tag and a `<figcaption></figcaption>`.

# Color

I've written notes from my 102 class and they can be found [here](https://kmangub.github.io/reading-notes/css-notes.html).

# Text

We have to keep in mind if the typeface is installed on the user's computer. 

Font sizes can be expressed in pixels, percentages, or ems. **Ems** is equivalent to the width of the letter m.

We can change the case of the text using the `text-transform: uppercase;` or the `text-transform: lowercase;` property. 

Line heights space out the paragraphs, making it more readable. We can achieve this by using the `line-height:` property.

Letters and word spacing can be added using the `letter-spacing` and `word-spacing` property.

Use the `text-align:` to move the text to the center or to the right.

Use the `vertical-align:` property to move the text relative to where the image is. 

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)