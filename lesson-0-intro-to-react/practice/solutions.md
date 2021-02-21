# Practice Exercises 8.0

0. In your own words, describe some of the features of React. What makes it so popular?

** Suggested Answer** Here are a few things you might consider:

React is a powerful component library for building complex User Interfaces. A few reasons why it's so popular:

  * Performance - the Virtual DOM allows us to see huge performance increases over classic DOM Manipulation
  * Declarative API - React is built to prefer declarative programming, mean you can build applications that say what should happen instead of how it happens.
  * Rich community - there are a lot of open source libraries and plugins that you can take advantage of, and it's also possible to write your own reusable extensions.

1. What is the difference between declarative and imperative programming? How can we use this in our applications?

** Suggested Answer**

With declarative programming, you want your code to say what it's doing instead of how it's doing it. Consider the process of summing all numbers in an array.

```js
const array = [1, 5, 7, 9]
let sum = 0
for (let i = 0; i < array.length; i++) {
  sum += array[i]
}
```

This would be an example of imperative programming - we're describing step by step what is happening. Compare that to the code below:

```js
const array = [1, 5, 7, 9]
const sum = array.reduce((sum, number) => sum + number );
```

or even:

```js

function sum(array, initialValue=0){
  return array.reduce((sum, number) => sum + number, initialValue);
}

// In another file somewhere
const array = [1, 5, 7, 9]
const total = sum(array);
```

Notice that, in all of these examples, the details of how our code is working still has to live somewhere. We've just chosen to abstract it away into other functions. Compare this to `ReactDOM.render` - you don't have to worry about how the rendering is happening, you just know that it is happening.

2. Using `React.createElement`, create an `h1` tag with an inner text of 'Hello World'.

```js
const h1 = React.createElement('h1', {}, 'Hello World')
```

3. Given an html page with a div that has an id of `app`, render the `h1` tag you created previously to the DOM.

```js
const h1 = React.createElement('h1', {}, 'Hello World')
ReactDOM.render(h1, document.getElementById('app'));
```

4. Using `React.createElement`, create a `div` with the following children:
  * An h1 with text of "Ice Cream Menu"
  * An unordered list with three list items inside. The list items should have inner text of "Chocolate", "Vanilla", and "Rocky Road"

```js
const app = React.createElement('div', {}, [
    React.createElement('h1', {}, 'Hello World'),
    React.createElement('ul', {}, [
      React.createElement('li', {}, 'Chocolate'),
      React.createElement('li', {}, 'Vanilla'),
      React.createElement('li', {}, 'Strawberry'),
    ])
  ])
ReactDOM.render(app, document.getElementById('app'));
```


