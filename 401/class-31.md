# Next.js

For setup, we need Node.js to be on ver. 10.13 or later.

We create a next app by inputting the following to our terminal:

```
npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/learn-starter"
```

We cd into the app and run the `npm run dev` command, then we go to our port 3000 on our web browser.

We will see the 'rocketship' equivalent on our local host. 

## Navigating Between Pages

We can use `<Link>` to wrap `<a>` tags to navigate to another page. 

First, we need to import the following:

```
import Link from 'next/link'
```

Then, find the h1 tag,

```
<h1 className="title">
  Learn <a href="https://nextjs.org">Next.js!</a>
</h1>
```

and change it to:

```
<h1 className="title">
  Read{' '}
  <Link href="/posts/first-post">
    <a>this page!</a>
  </Link>
</h1>
```

Inside of our `pages/posts/first-post.js` file:


```
import Link from 'next/link'

export default function FirstPost() {
  return (
    <>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </>
  )
}
```

## Assets, Metadata, and CSS

### Assets

Next.js can serve static assets under the top level directory. If we want to put an image inside of our webpage, we need to create an images directory inside of our public directory.

The image component can handle images, such as resizing, and optimizing. Below is an example of how we can use it:

```
import Image from 'next/image'

const YourComponent = () => (
  <Image
    src="/images/profile.jpg" // Route of the image file
    height={144} // Desired size with correct aspect ratio
    width={144} // Desired size with correct aspect ratio
    alt="Your Name"
  />
)
```

### Metadata

If we want to modify the `<title>` HTML tag, we can open the `pages/index.js` and edit the `<Head>`:

```
<Head>
  <title>Create Next App</title>
  <link rel="icon" href="/favicon.ico" />
</Head>
```

In our `pages/posts/first-post.js` file:

```
import Head from 'next/head'
```

Then add:

```
export default function FirstPost() {
  return (
    <>
      <Head>
        <title>First Post</title>
      </Head>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </>
  )
}
```

### CSS Styling

In React, we can use a styling library called `style-jsx`, which allows us to write CSS inside of a React component. Something to think about since we've worked with tailwindcss in our class. 

We can create a `layout` component that can be shared with all pages. To do this, we create a directory called `components` and create a file called `layout.js` that will contain the following:

```
export default function Layout({ children }) {
  return <div>{children}</div>
}
```

Next, we import our `layout.js`:

```
import Head from 'next/head'
import Link from 'next/link'
import Layout from '../../components/layout'

export default function FirstPost() {
  return (
    <Layout>
      <Head>
        <title>First Post</title>
      </Head>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </Layout>
  )
}
```

We create `components/layout.module.css` with the following content:

```
.container {
  max-width: 36rem;
  padding: 0 1rem;
  margin: 3rem auto 6rem;
}
```

To use the container:

1. Import the CSS file and assign a name to it, like styles
2. Use styles.container as the className

```
import styles from './layout.module.css'

export default function Layout({ children }) {
  return <div className={styles.container}>{children}</div>
}
```

Doing this will automatically generate class names.

### Global Styles


CSS Modules help with component-level styling and do that by using a global CSS file. 

First we create a file called `pages/_app.js` that contains the following:

```
export default function App({ Component, pageProps }) {
  return <Component {...pageProps} />
}
```

Then we would have to start the server again



