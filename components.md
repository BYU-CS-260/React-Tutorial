# Components
Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. 
This part of the tutorial provides an introduction to the idea of components. 
You can find a detailed component API reference [here](https://reactjs.org/docs/react-component.html).

Components are like JavaScript functions. 
They accept arbitrary inputs (called “props”) and return React elements describing what should appear in the DOM.

Start with a web page called "components.html" with the following content
```
<html>
  <head>
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
        <div id="root"></div>
  </body>
</html>
```
The simplest way to define a component is to write a JavaScript function:
```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

This function is a valid React component because it accepts a single “props” 
(which stands for properties) object argument with data and returns a React element. 
We call such components “function components” because they are literally JavaScript functions.

You can also use an [ES6](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes) class to define a component:
```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
These two components are equivalent from React’s point of view.

You are used to using HTML tags like ```<h1>``` or ```<ul>``` or ```<div>``` that have properties. 
```<div id="root"></div>``` has the property ```id``` passed to it.  
Components you write in React can also have properties that modify their rendering.

Insert code for your "Welcome" function into your HTML file.
```
  <script type="text/babel">  
  function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
  }

  const root = ReactDOM.createRoot(document.getElementById('root'));
  const element = <Welcome name="Sara" />;
  root.render(element);
</script>
```
## Composing Components
You can create a component that uses other components to create more complex HTML. 
Modify your HTML file to contain the following
```
  <script type="text/babel">  
  function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
  }
  function App() {
    return (
      <div>
        <Welcome name="Sara" />
        <Welcome name="Cahal" />
        <Welcome name="Edite" />
      </div>
    );
  }
  const root = ReactDOM.createRoot(document.getElementById('root'));
  root.render(<App />);
  </script>
  ```
  Add something to the React element to build your confidence.
  
  If you get stuck, you can find the working page [here](component.html).

[Next Tutorial](events.md)
