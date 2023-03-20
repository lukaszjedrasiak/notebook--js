By nesting components inside of other components, you can build infinitely complex architectures, even if each component is relatively simple. The relationship that you just built is the fundamental relationship of React.js.

Importing:
```js
import {ComponentName} from './path-to-component'

class SampleClass extends React.Component {

	sampleMethod() {
		// do sth
	}
	
	render() {
		return (
			// just calling
			<ImportedComponent />

			//calling with prop
			<ImportedComponent sampleProp='message' />

			//calling with function prop
			<ImportedComponent sampleProp={this.sampleMethod}
		)
	}
}

ReactDOM.render(<SampleClass />, document.getElementById('app'))
```

Exporting (named export):
```js
export class ComponentName extends React.Component {
	render() {
		// code here
	}
}
```

## component props

```js
const stringProps = JSON.stringify(this.props);
```

## passing props to component

Examples:
```js
//pass string
<Example message='secret info' />
```

```js
//pass array
<Example message={['item1', 'item2', 'item3']} />
```

## displaying sent props

Example:
```js
class SampleClass extends React.Component {
	render() {
		return <h1>{this.props.message}</h1>
	}
}
```

## default props

```js
	SampleClass.defaultProps = {message: 'default message'}
```