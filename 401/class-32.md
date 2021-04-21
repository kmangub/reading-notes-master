# Dynamic Routes

To make the page dynamic, we need to create a page called `[id].js`in our `pages/posts` directory. The `[` and `]` are considered dynamic routes in `Next.js`.

Inside of our `[id].js`, we'll put the following code just like our other pages:

```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}
```
What we are going to do that's new is we will export an `async` function called `getStaticPaths` from this page. We need to return a list of values for the `id`. Our file should now look like this:

```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}
```

and then implement `getStaticProps`:

```

Dynamic Routes
Page Path Depends on External Data
In the previous lesson, we covered the case where the page content depends on external data. We used getStaticProps to fetch required data to render the index page.

In this lesson, we’ll talk about the case where each page path depends on external data. Next.js allows you to statically generate pages with paths that depend on external data. This enables dynamic URLs in Next.js.

Page Path Depends on External Data
How to Statically Generate Pages with Dynamic Routes
In our case, we want to create dynamic routes for blog posts:

We want each post to have the path /posts/<id>, where <id> is the name of the markdown file under the top-level posts directory.
Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.
Overview of the Steps
We can do this by taking the following steps. You don’t have to make these changes yet — we’ll do it all on the next page.

First, we’ll create a page called [id].js under pages/posts. Pages that begin with [ and end with ] are dynamic routes in Next.js.

In pages/posts/[id].js, we’ll write code that will render a post page — just like other pages we’ve created.

import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}
Now, here’s what’s new: We’ll export an async function called getStaticPaths from this page. In this function, we need to return a list of possible values for id.

import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}
Finally, we need to implement getStaticProps again - this time, to fetch necessary data for the blog post with a given id. getStaticProps is given params, which contains id (because the file name is [id].js).

import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

export async function getStaticProps({ params }) {
  // Fetch necessary data for the blog post using params.id
}
```

When we add the function `getAllPostIds` function at the bottom, we have to keep in mind that the array that's passed is not a list of strings, but rather a list of objects

Next we need to get necessary data to render the post. We open our `posts.js` file 

```
import { getAllPostIds, getPostData } from '../../lib/posts'

export async function getStaticProps({ params }) {
  const postData = getPostData(params.id)
  return {
    props: {
      postData
    }
  }
}
```
Render markdown requires us to use the `remarks` library. So,

```
npm install remark remark-html
```

Then inside of our `posts.js`, import the following,

```
import remark from 'remark'
import html from 'remark-html'
```

Update the `getPostData()` in the same file,

```
export async function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`)
  const fileContents = fs.readFileSync(fullPath, 'utf8')

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents)

  // Use remark to convert markdown into HTML string
  const processedContent = await remark()
    .use(html)
    .process(matterResult.content)
  const contentHtml = processedContent.toString()

  // Combine the data with the id and contentHtml
  return {
    id,
    contentHtml,
    ...matterResult.data
  }
}
```
Use `await` since we are using an async function,

```
export async function getStaticProps({ params }) {
  // Add the "await" keyword like this:
  const postData = await getPostData(params.id)
  // ...
}
```

Then we update the `Post` component in `pages/posts/[id].js` to render `contentHtml` using `dangerouslySetInnerHTML`,

```
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
      <br />
      <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
    </Layout>
  )
}
```

# Deploying the Next.js App
1. We need to push our code to GitHub.
2. Install Vercel for GitHub
3. Create an account with Vercel, which is a platform that has has a Global CDN supporting static and JAMstack deployments and serverless functions. 
4. Import our repo on Vercel and it's okay to use default values. We will get a deployment URL.

