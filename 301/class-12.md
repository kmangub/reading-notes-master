# Partials

Partials are like functions that can create dynamic changes as oppose to making small changes for each web page. Partials are a great way to use the same web layout across multiple pages where you have the nav bar and website title static across the board. 

The partials directory will live inside of the views directory and will contain a file called `navbar.ejs`, which will just contain the HTML navbar, and a `footer.ejs`, which will contain the HTML for the footer. 

Once we created that, we are now ready to implement it to the page. To use the partials, we will use the delimiters, or strawberries, to post it to the webpage; the syntax will look like this:

```
    <body>
        <div class="container">
            <%- include('partials/navbar') %>
            <div class="jumbotron">
                <h1>All about Node</h1>
                <p class="lead">Check out our articles below!</p>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <div class="list-group">
                      <!-- loop over blog posts and render them -->
                      LIST_OF_POSTS
                    </div>
                </div>
            </div>
            <%- include('partials/footer') %>
        </div>
    </body>
```

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)