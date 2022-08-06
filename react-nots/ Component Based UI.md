 # Component Based UI 

 **react hello world**
 

React is a JavaScript library created by Facebook ,React is a User Interface (UI) library ,React is a tool for building UI components   \


The smallest React example looks like this:   

```
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);
```


A React Element is what gets returned from components. It's an object that virtually describes the DOM nodes that a component represents. With a function component, this element is the object that the function returns. With a class component, the element is the object that the component's render function returns.    



**JSX**

What is JSX?

JSX stands for JavaScript XML.

JSX allows us to write HTML in React.

JSX makes it easier to write and add HTML in React.

JSX allows us to write HTML elements in JavaScript and place them in the DOM without any createElement()  and/or appendChild() methods.

__Embedding Expressions in JSX__

In the example below, we declare a variable called name and then use it inside JSX by wrapping it in curly braces:
```
const name = 'Josh Perez';const element = <h1>Hello, {name}</h1>;
```

**Rendering Elements**

Elements are the smallest building blocks of React apps.

An element describes what you want to see on the screen:
```
const element = <h1>Hello, world</h1>;
```

