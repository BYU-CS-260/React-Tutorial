# Events
Handling events in React is very similar to handling events in javascript except that
React events are named using camelCase, rather than lowercase and you pass a function as the event handler, rather than a string.

With HTML, you would handle the "button" event with
```
<button onclick="activateLasers()">
  Activate Lasers
</button>
```
Would become
```
<button onClick={activateLasers}>
  Activate Lasers
</button>
```
You must also call "preventDefault()" on the event to keep the default behavior from happening.
```
function Form() {
  function handleSubmit(e) {
    e.preventDefault();
    alert('You clicked submit.');
  }

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
```
For this part of the tutorial, you will create a component that creates a "Submit" button and a component that toggles the label on a button from "OFF" to "ON".

Start with a web page called "events.html" with the following content
```
<html>
  <head>
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">  
    
    const root = ReactDOM.createRoot(document.getElementById('root'));
    root.render(<Form />);
    </script>
  </body>
</html>
```
Add a form with a submit button and test that it works on your server.

At times you will want to maintain state between events.  A good way to do this is to create a object.  
"this" is used to access object data.  The "state" object has the "isToggleOn" variable that determines if 
the button should display "ON" or "OFF".
```
class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isToggleOn: true};

    // This binding is necessary to make `this` work in the callback
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(prevState => ({
      isToggleOn: !prevState.isToggleOn
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.isToggleOn ? 'ON' : 'OFF'}
      </button>
    );
  }
}
```
You will have to change the render to
```
root.render(<Toggle />);
```
Test this code to make sure you can toggle the button on your server.

Now create a component called ```<Both \>``` that returns both the form and the button.

Test this code to make sure you can submit the form and toggle the button on your server.
  
Add something to the React element to build your confidence.
  
If you get stuck, you can find the working page [here](events.html).
  
[Next Tutorial](conditional.md)
