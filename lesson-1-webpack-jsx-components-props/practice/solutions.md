2. What is the purpose of Babel in developing JavaScript applications? How does it make our lives easier?

There are many different browsers across many different operating systems, and each one could be running a slightly different version of JavaScript. Babel allows us to take advantage of modern JS features while still producing code that will be backwards compatible. This happens through transpiling - taking the JS code that we write, and producing JS code that will run on older browsers.

6. Write a function called `App` that returns the element you created in the previous example. Use the function to render into the DOM instead of the element.

```js

const App = () => {
  return React.createElement('div', {}, [
      React.createElement('h1', {}, 'Hello World'),
      React.createElement('ul', {}, [
        React.createElement('li', {}, 'Chocolate'),
        React.createElement('li', {}, 'Vanilla'),
        React.createElement('li', {}, 'Strawberry'),
      ])
    ])
}
ReactDOM.render(App(), document.getElementById('app'));
```

7. Update your `App` function to take in an argument called `props`. Props should have two keys:
  * `title`: a string to represent the page title (use in the text of the h1)
  * `flavors`: an array of strings, each one representing an ice cream flavor.
Change your function so that it can render that data dynamically.

```js
const App = (props) => {
  const { title, flavors } = props;
  return React.createElement('div', {}, [
      React.createElement('h1', {}, title),
      React.createElement('ul', {}, flavors.map(flavor => React.createElement('li', {}, flavor)))
    ])
}
ReactDOM.render(App({title: 'Hello!', flavors: ['Mint']}), document.getElementById('app'));
```

8. Add Babel to your project following the guide here. This will allow us to write JSX so we don't have to keep using `React.createElement`. Update your code to use JSX.


```js
const App = ({title, flavors}) => {
  return (
    <div>
      <h1>{title}</h1>
      <ul>{flavors.map(flavor => <li>{flavor}</li>) }</ul>
    </div>
  )
}
ReactDOM.render(<App title="Hello World!" flavors={["Mint Chip", "Cookie Dough"]} />, document.getElementById('app'));
```