# Conditional Rendering
You can use the same conditional statements in React that you use with javascript.

This part of the tutorial will explore how you can use conditional statements to render different components depending on state.

Start by creating a page called "conditional.html" with the following content:
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
    root.render(<Greeting isLoggedIn={true}/>);
    </script>
  </body>
</html>
```
Now create a component that will render differently depending on the property.
```
      function Greeting(props) {
        const isLoggedIn = props.isLoggedIn;
        if (isLoggedIn) {
          return <h1>Welcome back!</h1>;
        }
        return <h1>Please sign up.</h1>;
      }
```
Experiment with changing the value of "isLoggedIn" from "true" to "false".

Now create some button components.  We will pass them the event handler.
```
      function LoginButton(props) {
        return (
          <button onClick={props.onClick}>
            Login
          </button>
        );
      }
      
      function LogoutButton(props) {
        return (
          <button onClick={props.onClick}>
            Logout
          </button>
        );
      }
```
And then create an object that will maintain state
```
      class LoginControl extends React.Component {
      constructor(props) {
        super(props);
        this.handleLoginClick = this.handleLoginClick.bind(this);
        this.handleLogoutClick = this.handleLogoutClick.bind(this);
        this.state = {isLoggedIn: false};
      }
    
      handleLoginClick() {
        this.setState({isLoggedIn: true});
      }
    
      handleLogoutClick() {
        this.setState({isLoggedIn: false});
      }
    
      render() {
        const isLoggedIn = this.state.isLoggedIn;
        let button;
        if (isLoggedIn) {
          button = <LogoutButton onClick={this.handleLogoutClick} />;
        } else {
          button = <LoginButton onClick={this.handleLoginClick} />;
        }
    
        return (
          <div>
            <Greeting isLoggedIn={isLoggedIn} />
            {button}
          </div>
        );
      }
    }
```
You will need to change the render statement to
```
    root.render(<LoginControl/>);
```
Add something to the React element to build your confidence.
  
If you get stuck, you can find the working page [here](conditional.html).
  
[Next Tutorial](lists.md)
