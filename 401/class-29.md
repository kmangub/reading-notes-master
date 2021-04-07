# ES6 Overview

Source: https://www.taniarascia.com/es6-syntax-and-feature-overview/

Basically Javascript.

This is a review of what we learned in 301, but it's a good reminder. 
Some of the key features include variable declaration such as `let` and `const`, arrow function syntax, promises and callbacks.

# Hello World React

Source: https://reactjs.org/docs/hello-world.html

React is a JavaScript Library.

Here's a taste of what React looks like:

```
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```
Which displays a hello world on the webpage.

# Intro JSX

Source: https://reactjs.org/docs/introducing-jsx.html

JavaScript XML (JSX) is a syntax extension to JavaScript. Consider the following:

```
const element = <h1>Hello, world!</h1>;
```
This is not a string or HTML.

React separates concerns with loosely coupled units called “components” that contain both.

# Rendering Elements
Source: https://reactjs.org/docs/rendering-elements.html

Elements in react are objects and are cheap to create. We can also update the rendered element by creating a new element and passing it to `ReactDOM.render()`

# Components and prompts

Source: https://reactjs.org/docs/components-and-props.html

Components are pieces we can re-use in our code. Below are some examples of components using JavaScript.

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

We can render, compose, and extract components. 

Props are read only, meaning that we must never modify its own props

# State and Lifecycle

Source: https://reactjs.org/docs/state-and-lifecycle.html

We can add a local state to a class and add lifecycles methods to them as well. Below are examples of lifecycle methods:

```
componentDidMount() {
  }

  componentWillUnmount() {
  }
```

- The `componentDidMount()` method runs after the component output has been rendered to the DOM
- The `componentWillUnmount()` breaks the method. 

# Handling Events 

Source: https://reactjs.org/docs/handling-events.html

- React events are named using camelCase, rather than lowercase.
- With JSX you pass a function as the event handler, rather than a string.

In HTML:

```
<button onclick="activateLasers()">
  Activate Lasers
</button>
```

In React:
```
<button onClick={activateLasers}>
  Activate Lasers
</button>
```

