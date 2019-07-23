---
title: Class Components
author: Kunlei Lian
updated: 07/23/2019
---

Components are the core of React applications. 
There are two types of components: *functional components* and *class components*.
This article focuses on class components.

## Class Components
Class components are defined using keyword *class* and must extend the *React.Component*.
Similar to functional components, class components must define a *render* function that returns a JSX block.
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
}

export default App;
```

The code block returned by *render()* is actually not html but JavaScript xml.
The `<div></div>` is an example syntax that is redefined by the React team to resemble the html syntax.
The code block of the *return* function is equivalent to 
```javascript
    return React.createElement('div', null, React.createElement('h1', null, "Hi, I am a React App!!!"));
```

There are two restrictions of the JSX syntax:

* we cannot use *class* to style a JSX element because *class* is used as a keyword to define class components. Instead, we use *className* within a React application.
* we can have only one root element within the return statement.


### Using states within class components
Class components can have states that change over time and every state change triggers the JSX defined in the *render* function being updated.

Below is the updated *App* component using states.
```javascript
class App extends React.Component {
  state = {
    persons: [
      { name: "Max", age: 28 },
      { name: "Manu", age: 29 },
      { name: "Stephanie", age: 26 },
    ],
  }

  render() {
    return (
      <div>
        <h1>Hi, I am a React app!</h1>
        <button>Witch Name</button>
        <Person
          name={this.state.persons[0].name}
          age={this.state.persons[0].age}
        />
        <Person
          name={this.state.persons[1].name}
          age={this.state.persons[1].age}
        >
          My hobbies: racing
        </Person>
        <Person
          name={this.state.persons[2].name}
          age={this.state.persons[2].age}
        />
      </div>
    );
  }
}
```