# Sending Form Data

Forms are filled out by the user and it gets sent to the server via client/server architecture. To send the data, the `<form>` element needs to specify the attribute `action` or `method`.

- `action` - Defines where the data gets sent. The value can be a relative or an absolute URL. 

> An example of absolute URL is `<form action="https://example.com">` and a relative URL is `<form action="/somewhere_else">`

**HTTPS (secure HTTP)** means that the data is encrypted with the request. However, if the user is on a secure page and gets directed to a HTTP URL, the user will get a security warning because it will try to send the data when it's not encrypted, which is risky.

**Get Method** is where the browser communicates with the server and gets sent to an empty body. The form sends data and also appends it to the URL.

**Post Method** is similar to the get method. The browser asks the server to look at the data sent and spits back the results. The data doesn't carry over to the URL.

We can view the HTTP requests in the browser by following these steps:

1. Open the developer tools.
2. Select "Network"
3. Select "All"
4. Select "foo.com" in the "Name" tab
5. Select "Headers"

> This only works if the method is a get method. This will not work with the post method. 

## Security Issues
When bulding a webpage, we have to limit the capabilities, or sandbox, the users so that we can prevent malicious intent that can compromise the page. Here are some general rules to remember to prevent any issues:

1. Never trust your users.
2. Escape potentially dangerous characters.
3. Limit the incoming amount of data to allow only what's necessary.
4. Sanbox uploaded files.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)