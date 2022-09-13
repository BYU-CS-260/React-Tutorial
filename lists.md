# Lists
Displaying lists in React uses the "map" function in javascript.  
Let's investigate how to create a ```<ul>``` block using React.
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
```
Create a file on your server called "lists.html" with the following content.
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
    root.render(<Numbers />);
    </script>
  </body>
</html>
```
Now add a block to create an unordered list of the numbers 1 through 5.
```
    function Numbers() { 
      const numbers = [1, 2, 3, 4, 5];
      const listItems = numbers.map((number) =>
        <li>{number}</li>
      );
      return(<ul>{listItems}</ul>)
    }
```
Test this code to make sure you can display the list of numbers from the array on your server.
  
Add something to the React element to build your confidence.
  
If you get stuck, you can find the working page [here](lists.html).
  
[Next Tutorial](forms.md)
