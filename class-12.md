# Local Storage

- In the past, cookies were invented because they the browsers needed some way to store data. The downsides are that cookies come included with every HTTP requests, meaning that it slows down the application. In addition, it sends unencrypted data over the internet.

- `userdata` makes it so that the webpage can store about 64 KB per domain.

- With Gears, it's possible to have unlimited amounts of data per domain.

- HTML5 Storage allows web pages to save stored data and are able to come back to it with the changes still intact.

- HTML5 Storage is based on key/value pairs. Named keys are strings. We use functions like `parseInt()` and `parseFloat()` to extract the data.

- Tracking the storage data is made possible using the `storage` event.  It is supported on all browsers.

## Storageevent Objects

- key - string - the named key that was added, removes, or modified.

- oldValue - any - The previous value, or null if a new item was added.

- newValue - any - the new value, or null if an item was removed.

- url - string - the page which called a method that triggered this change


[Back to Home Page](https://kmangub.github.io/reading-notes-master/)