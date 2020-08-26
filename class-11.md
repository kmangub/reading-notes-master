# Charts

Charts are used to quickly show data using visual aids. Common types of charts are bar graphs, pie charts, and line graphs. The graphs contain a `<canvas>` tag with a width and height; this is how we render the chart to our webpage. Using a `chart.js` file, we can generate graphs in our HTML files. 

>Disclaimer: All lines of code are taken from https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/

To get started, we input the code below, taken from the Chart.min.js file:


``` 
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <title>Chart.js demo</title>
        <script src='Chart.min.js'></script>
    </head>
    <body>
    </body>
</html>
```

From here, we can create different types of charts. 

To make line charts, we use the `<canvas>` tag as shown below:

```
<canvas id="buyers" width="600" height="400"></canvas>
```

Then we grab the content of the graph using the code below:

```
<script>
    var buyers = document.getElementById('buyers').getContext('2d');
    new Chart(buyers).Line(buyerData);
</script>
```
Finally, we create the data as well as giving color properties to the graph:

```
var buyerData = {
	labels : ["January","February","March","April","May","June"],
	datasets : [
		{
			fillColor : "rgba(172,194,132,0.4)",
			strokeColor : "#ACC26D",
			pointColor : "#fff",
			pointStrokeColor : "#9DB86D",
			data : [203,156,99,251,305,247]
		}
	]
}
```

Similarly, we can create pie charts and bar charts using the same algorithm. 

# Canvas Element

The `<canvas>` tag opens up the environment for new possibilities. With the tag, we can create shapes and essentially draw on our webpage. For drawing rectangles, we will work on the coordinate space (x,y).

- `fillRect()` - Draws a large black square 100 pixels on each side

- `clearRect()` - Erases a square from the center

- `strokeRect()` - Create a rectangular outline the desired pixels within the square.

To add color, we use `fillStyle`, which sets the style used when filling shapes, and `strokeStyle`, which sets  the outline.

We can even draw texts using:

- `fillText(text, x, y [, maxWidth])` - Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.

- `strokeText(text, x, y [, maxWidth])` - Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)