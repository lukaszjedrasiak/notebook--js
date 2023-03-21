Example:
```js
class Example extends React.Component {  
  constructor(props) {  
    super(props);  
    this.state = { mood: 'decent' };  
	this.makeSomeFog = this.makeSomeFog.bind(this);
  }

  makeSomeFog() {  
    this.setState({  
      mood: 'foggy'  
    });
  
  render() {  
    return <div></div>;  
  }  
}  
  
<Example />
```