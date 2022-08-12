# Hello World
Lets get started with the simplest React page, "Hello World".  Start by creating a basic page and loading the React modules.
```
<html>
  <head>
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
  </body>
</html>
```
Now add a `<div>` to `<body>` that React will populate.  When you run `render`, React will create html and put it into this div.
```
      <div id="mydiv"></div>
```
Now add the javascript to put "Hello World" into this `<div>`.  Put the `<script>` at the bottom of the `<body>`.  Notice that we are using `getElementById` to find the <div> in the DOM.
We then render `element` in that part of the DOM.
```
      <script type="text/babel">
        const root = ReactDOM.createRoot(
            document.getElementById('mydiv')
        );
        const element = <h1>Hello, world</h1>;
        root.render(element);    
    </script>
```
Test to make sure that you are seeing the element in your browser when you access your web servers URL for the subdirectory where this file is found.
  
Now create a more complex element with multiple tags.  Experiment by adding some new HTML to the element.
```
        const element = (
          <div>
          <h1>Hello, world</h1>
          <h2>Goodbye, world</h2>
          </div>
        )
```
If you get stuck, you can find the working page [here](hello.html).
  
[Next Tutorial](rendering.md)
