A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML.

A React component should use `props` to store information that can be changed, but can only be changed by a _different_ component.

A React component should use `state` to store information that the component itself can change.

[component props](component-props)
[component states](component-states)

## class components

```js
// import library
import React from 'react';
import ReactDOM from 'react-dom';

const fiftyFifty = Math.random() < 0.5;

// create component class
class MyComponentClass extends React.Component {

	constructor(props) {
		super(props);
		this.state = { // state here }
	}

	myFunc() {
		alert('alert');
	}
	
	render() {
		// add some logic
		let subtitle;
		fiftyFifty ? subtitile = "toss" : subtitle = "coin"

		return (
			<div onHover={this.myFunc}>
				<h1>Hello world</h1>
				<span>{subtitle}</span>
			</div>
		)
	}

	componentDidMount() {
		// 
	}

	componentWillUnmount() {
		// 
	}

	componentDidUpdate() {
		//
	}
}

//create component instance
<MyComponentClass />

//render component
ReactDOM.render(
	<MyComponentClass />,
	document.getElementById('app')
);
```

Subclassing `React.Component`, is creating a new _component class_. This is not a component! A component class is more like a factory that produces components. When you start making components, each one will come from a component class.

> Component class variable names must begin with capital letters in order to distinguish it between standard HTML tags.

### render function

There is only one property that you _have to_ include in your instructions: a _render method._

A render method is a property whose _name_ is `render`, and whose _value_ is a function. The term “render method” can refer to the entire property, or to just the function part.

A render method must contain a `return` statement. Usually, this `return` statement returns a JSX expression.

### component instance

`MyComponentClass` is now a working _component class!_ It’s ready to follow its instructions and make some React components.

So, let’s make a React component! It only takes one more line:

```js
<MyComponentClass />
```

To make a React component, you write a _JSX element._ Instead of naming your JSX element something like `h1` or `div` like you’ve done before, give it the same name as a _component class_. Voilà, there’s your _component instance!_

JSX elements can be either HTML-like, or _component instances_. JSX uses capitalization to distinguish between the two! _That_ is the React-specific reason why component class names must begin with capital letters. In a JSX element, that capitalized first letter says, “I will be a component instance and not an HTML tag.”

### render a component

```js
ReactDOM.render(  
  <MyComponentClass />,  
  document.getElementById('app')  
);
```

> `ReactDOM.render()` will tell `<MyComponentClass />` to call _its_ render method.

## functional components

```js
// A component class written in the usual way:
export class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}

// The same component class, written as a stateless functional component:
export const MyComponentClass = props => {
  return (
	  <h1>Hello world</h1>;
	  <p>{props.someProps}</p>
  )
}

// Works the same either way:
ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```