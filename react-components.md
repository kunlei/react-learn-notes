---
title: React Components
author: Kunlei Lian
---

Components are the core of React applications. 
There are two types of components: *functional components* and *class components*.

## Functional Components
A functional component can be created in multiple ways:

Option 1:
```javascript
function person() {
    return <p>person</p>
}
```

Option 2:
```javascript
const person = function() {
    return <p>person</p>
}
```

Option 3:
```javascript
const person = () => {
    return <p>person</p>
}
```

Option 3 is the recommended way.

## Class Components
Below is an example of class component:

```javascript
import React from 'react';

class App extends React.Component {
    render() {
        return (
            <div>
                <h1>Hello World!</h1>
            </div>
        );
    }

    // return React.createElement('div', null, React.createElement('h1', null, "Hi, I am a React App!!!"));
}

export default App;
```

One thing to remember is that a class component must extend *React.Component* and must provide a *render()* method which return a block of JSX.
The code block returned by *render()* is actually not html but JavaScript xml.
The `<div></div>` is an example syntax that is redefined by the React team to resemble the html syntax.

There are two restrictions of the JSX syntax:

* we cannot use *class* to style a JSX element because *class* is used as a keyword to define class components.
* we can have only one root element within the return statement.