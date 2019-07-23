---
title: Functional Components
author: Kunlei Lian
updated: 07/23/2019
---

Components are the core of React applications. 
There are two types of components: *functional components* and *class components*.
This article focuses on functional components.

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

### Using props with functional components
A functional component can take inputs from upper level components and use them in the rendering function.
For example, the *Person* component can take properties of name and age and render contents differently based on inputs.
```javascript
const person = (props) => {
    return (
        <p>I am {props.name} and I am {props.age}</p>
    );
}
```

In the invoking component, the properties must be provided within the starting bracket.
```javascript
import Person from './Person/Person';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>Hi, I am a React app!</h1>
        <p>This is really working!</p>
        <Person name="Max" age="28" />
      </div>
    );
  }
}
```

Note that *props* in functional components don't have *this.* as prefix.


### Using children with functional components
The *props* has a special attribute called *children* which represents the elements enclosed between the starting and ending bracket of the functional element being called.
For example, the *Person* component can render its children element by accessing *props.children*.
```javascript
const person = (props) => {
    return (
        <div>
            <p>I am {props.name} and I am {props.age}</p>
            <p>{props.children}</p>
        </div>
        
    );
}
```

In the invoking component, the children is passed as follows:
```javascript
class App extends React.Component {
  render() {
    return (
      <div>
        <h1>Hi, I am a React app!</h1>
        <p>This is really working!</p>
        <Person name="Max" age="28" />
        <Person name="Manu" age="29">My hobbies: racing</Person>
        <Person name="Stephanie" age="26" />
      </div>
    );
  }
}
```






