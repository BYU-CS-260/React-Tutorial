# Rendering
Elements are the smallest building block of a React page.  
Start by creating a web page called "rendering.html" with a div called "root" that React will populate.
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
Applications built with just React usually have a single root DOM node. 
If you are integrating React into an existing app, you may have many isolated root DOM nodes.

Now add code after the div to render an element with multiple HTML statements.  
Notice that the function "tick" is called every second because we pass it to the "setInterval" function.
```
<script type="text/babel">
const root = ReactDOM.createRoot(
  document.getElementById('root')
);

function tick() {
  const element = (
    <div>
      <h1>Time of Day</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  root.render(element);
}
setInterval(tick, 1000);
</script>
```
React compares the element and its children to the previous one, 
and only changes the parts of the DOM that need to be updated.

Change something in the script so that you are confident you know how an element is rendered.

If you get stuck, you can find the working page [here](rendering.html).

  
[Next Tutorial](components.md)
