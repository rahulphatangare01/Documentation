# React Basic interview Questions

<details>
<summary>
1.  <b>What is React? </b>
</summary>
React (aka React.js or ReactJS) is an open-source front-end JavaScript library that is used for building composable user interfaces, especially for single-page applications. It is used for handling view layer for web and mobile apps based on components in a declarative approach.
</details>

<details>
<summary>
2.  <b>What are the major features of React? </b>
</summary>
The major features of React are:

Uses **JSX** syntax, a syntax extension of JS that allows developers to write HTML in their JS code.

- It uses **Virtual DOM** instead of Real DOM considering that Real DOM manipulations are expensive.
- Supports **server-side rendering** which is useful for Search Engine Optimizations(SEO).
- Follows **Unidirectional or one-way** data flow or data binding.
- Uses **reusable/composable** UI components to develop the view.
</details>

<details>
<summary>
3.  <b> What is JSX? </b>
</summary>

_JSX_ stands for _JavaScript XML_ and it is an XML-like syntax extension to ECMAScript. Basically it just provides the syntactic sugar for the `React.createElement(type, props, ...children)` function, giving us expressiveness of JavaScript along with HTML like template syntax.

    In the example below, the text inside `<h1>` tag is returned as JavaScript function to the render function.

```jsx harmony
export default function App() {
  return <h1 className="greeting">{"Hello, this is a JSX Code!"}</h1>;
}
```

If you don't use JSX syntax then the respective JavaScript code should be written as below,

```javascript
import { createElement } from "react";

export default function App() {
  return createElement(
    "h1",
    { className: "greeting" },
    "Hello, this is a JSX Code!"
  );
}
```

 <details><summary><b>See Class</b></summary>
     <p>
    
```jsx harmony
              class App extends React.Component {
            render() {
                return <h1 className="greeting">{"Hello, this is a JSX Code!"}</h1>;
            }
            }
 ```
</p>
     </details>
</details>

<details>
<summary>
4.  <b> What is the difference between Element and Component?</b>
</summary>

An _Element_ is a plain object describing what you want to appear on the screen in terms of the DOM nodes or other components. _Elements_ can contain other _Elements_ in their props. Creating a React element is cheap. Once an element is created, it cannot be mutated.

The JavaScript representation(Without JSX) of React Element would be as follows:

```javascript
const element = React.createElement("div", { id: "login-btn" }, "Login");
```

and this element can be simiplified using JSX

    ```html
    <div id="login-btn">Login</div>
    ```

The above `React.createElement()` function returns an object as below:

```javascript
    {
      type: 'div',
      props: {
        children: 'Login',
        id: 'login-btn'
      }
    }
```

Whereas a **component** can be declared in several different ways. It can be a class with a `render()` method or it can be defined as a function. In either case, it takes props as an input, and returns a JSX tree as the output:

```javascript
const Button = ({ handleLogin }) => (
  <div id={"login-btn"} onClick={handleLogin}>
    Login
  </div>
);
```

Then JSX gets transpiled to a `React.createElement()` function tree:

```javascript
const Button = ({ handleLogin }) =>
  React.createElement(
    "div",
    { id: "login-btn", onClick: handleLogin },
    "Login"
  );
```

</details>

<details>
<summary>
5.  <b> How to create components in React? </b>
</summary>

Components are the building blocks of creating User Interfaces(UI) in React. There are two possible ways to create a component.

1. **Function Components:** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as the one and only one parameter and return React elements to render the output:

```jsx harmony
function Greeting({ message }) {
  return <h1>{`Hello, ${message}`}</h1>;
}
```

2. **Class Components:** You can also use ES6 class to define a component. The above function component can be written as a class component:

```jsx harmony
class Greeting extends React.Component {
  render() {
    return <h1>{`Hello, ${this.props.message}`}</h1>;
  }
}
```

</details>

<details>
<summary>
6.  <b>What is state in React? </b>
</summary>
   
 _State_ of a component is an object that holds some information that may change over the lifetime of the component. The important point is whenever the state object changes, the component re-renders. It is always recommended to make our state as simple as possible and minimize the number of stateful components.

Let's take an example of **User** component with `message` state. Here, **useState** hook has been used to add state to the User component and it returns an array with current state and function to update it.

```jsx harmony
import { useState } from "react";

function User() {
  const [message, setMessage] = useState("Welcome to React world");

  return (
    <div>
      <h1>{message}</h1>
    </div>
  );
}
```

Whenever React calls your component or access `useState` hook, it gives you a snapshot of the state for that particular render.

<details><summary><b>See Class</b></summary>
    <p>

```jsx harmony
import React from "react";
class User extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      message: "Welcome to React world",
    };
  }

  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    );
  }
}
```

 </p>
    </details>

    State is similar to props, but it is private and fully controlled by the component ,i.e., it is not accessible to any other component till the owner component decides to pass it.

</details>

<details>
<summary>
7.  <b>What are props in React? </b>
</summary>

_Props_ are inputs to components. They are single values or objects containing a set of values that are passed to components on creation similar to HTML-tag attributes. Here, the data is passed down from a parent component to a child component.

The primary purpose of props in React is to provide following component functionality:

    1. Pass custom data to your component.
    2. Trigger state changes.
    3. Use via `this.props.reactProp` inside component's `render()` method.

For example, let us create an element with `reactProp` property:

```jsx harmony
<Element reactProp={"1"} />
```

This `reactProp` (or whatever you came up with) attribute name then becomes a property attached to React's native props object which originally already exists on all components created using React library.

```jsx harmony
props.reactProp;
```

For example, the usage of props in function component looks like below:

```jsx
import React from "react";
import ReactDOM from "react-dom";

const ChildComponent = (props) => {
  return (
    <div>
      <p>{props.name}</p>
      <p>{props.age}</p>
      <p>{props.gender}</p>
    </div>
  );
};

const ParentComponent = () => {
  return (
    <div>
      <ChildComponent name="John" age="30" gender="male" />
      <ChildComponent name="Mary" age="25" geneder="female" />
    </div>
  );
};
```

The properties from props object can be accessed directly using destructing feature from ES6 (ECMAScript 2015). It is also possible to fallback to default value when the prop value is not specified. The above child component can be simplified like below.

```jsx harmony
const ChildComponent = ({ name, age, gender = "male" }) => {
  return (
    <div>
      <p>{name}</p>
      <p>{age}</p>
      <p>{gender}</p>
    </div>
  );
};
```

**Note:** The default value won't be used if you pass `null` or `0` value. i.e, default value is only used if the prop value is missed or `undefined` value has been passed.

  <details><summary><b>See Class</b></summary>
     The Props accessed in Class Based Component as below

```jsx
import React from "react";
import ReactDOM from "react-dom";

class ChildComponent extends React.Component {
  render() {
    return (
      <div>
        <p>{this.props.name}</p>
        <p>{this.props.age}</p>
        <p>{this.props.gender}</p>
      </div>
    );
  }
}

class ParentComponent extends React.Component {
  render() {
    return (
      <div>
        <ChildComponent name="John" age="30" gender="male" />
        <ChildComponent name="Mary" age="25" gender="female" />
      </div>
    );
  }
}
```

  </details>
</details>

<details>
<summary>
8.  <b>What is the difference between state and props?
 </b>
</summary>

In React, both `state` and `props` are plain JavaScript objects and used to manage the data of a component, but they are used in different ways and have different characteristics.

The `state` entity is managed by the component itself and can be updated using the setter(`setState()` for class components) function. Unlike props, state can be modified by the component and is used to manage the internal state of the component. i.e, state acts as a component's memory. Moreover, changes in the state trigger a re-render of the component and its children. The components cannot become reusable with the usage of state alone.

On the otherhand, `props` (short for "properties") are passed to a component by its parent component and are `read-only`, meaning that they cannot be modified by the own component itself. i.e, props acts as arguments for a function. Also, props can be used to configure the behavior of a component and to pass data between components. The components become reusable with the usage of props.

</details>

<details>
<summary>
9.  <b>What are synthetic events in React? </b>
</summary>

`SyntheticEvent` is a cross-browser wrapper around the browser's native event. Its API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers. The native events can be accessed directly from synthetic events using `nativeEvent` attribute.

Let's take an example of BookStore title search component with the ability to get all native event properties

```js
function BookStore() {
  function handleTitleChange(e) {
    console.log("The new title is:", e.target.value);
    // 'e' represents synthetic event
    const nativeEvent = e.nativeEvent;
    console.log(nativeEvent);
    e.stopPropagation();
    e.preventDefault();
  }

  return <input name="title" onChange={handleTitleChange} />;
}
```

</details>

<details>
<summary>
10.  <b>What are Pure Components? </b>
</summary>

Pure components are the components which render the same output for the same state and props. In function components, you can achieve these pure components through memoized `React.memo()` API wrapping around the component. This API prevents unnecessary re-renders by comparing the previous props and new props using shallow comparison. So it will be helpful for performance optimizations.

But at the same time, it won't compare the previous state with the current state because function component itself prevents the unnecessary rendering by default when you set the same state again.

The syntactic representation of memoized components looks like below,

```jsx
    const MemoizedComponent = memo(SomeComponent, arePropsEqual?);
```

Below is the example of how child component(i.e., EmployeeProfile) prevents re-renders for the same props passed by parent component(i.e.,EmployeeRegForm).

```jsx
import { memo, useState } from "react";

const EmployeeProfile = memo(function EmployeeProfile({ name, email }) {
  return (
    <>
      <p>Name:{name}</p>
      <p>Email: {email}</p>
    </>
  );
});
export default function EmployeeRegForm() {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  return (
    <>
      <label>
        Name: <input value={name} onChange={(e) => setName(e.target.value)} />
      </label>
      <label>
        Email:{" "}
        <input value={email} onChange={(e) => setEmail(e.target.value)} />
      </label>
      <hr />
      <EmployeeProfile name={name} />
    </>
  );
}
```

In the above code, the email prop has not been passed to child component. So there won't be any re-renders for email prop change.

In class components, the components extending _`React.PureComponent`_ instead of _`React.Component`_ become the pure components. When props or state changes, _PureComponent_ will do a shallow comparison on both props and state by invoking `shouldComponentUpdate()` lifecycle method.

**Note:** `React.memo()` is a higher-order component.

</details>

<details>
<summary>
11.  <b>What are inline conditional expressions? </b>
</summary>

You can use either _if statements_ or _ternary expressions_ which are available from JS to conditionally render expressions. Apart from these approaches, you can also embed any expressions in JSX by wrapping them in curly braces and then followed by JS logical operator `&&`.

```jsx harmony
<h1>Hello!</h1>;
{
  messages.length > 0 && !isLogin ? (
    <h2>You have {messages.length} unread messages.</h2>
  ) : (
    <h2>You don't have unread messages.</h2>
  );
}
```

</details>

<details>
<summary>
12.  <b> What is "key" prop and what is the benefit of using it in arrays of elements? </b>
</summary>

A `key` is a special attribute you **should** include when mapping over arrays to render data. _Key_ prop helps React identify which items have changed, are added, or are removed.

Keys should be unique among its siblings. Most often we use ID from our data as _key_:

```jsx harmony
const todoItems = todos.map((todo) => <li key={todo.id}>{todo.text}</li>);
```

When you don't have stable IDs for rendered items, you may use the item _index_ as a _key_ as a last resort:

```jsx harmony
const todoItems = todos.map((todo, index) => <li key={index}>{todo.text}</li>);
```

</details>

<details>
<summary>
13.  <b> What is Virtual DOM? </b>
</summary>

The _Virtual DOM_ (VDOM) is an in-memory representation of _Real DOM_. The representation of a UI is kept in memory and synced with the "real" DOM. It's a step that happens between the render function being called and the displaying of elements on the screen. This entire process is called _reconciliation_.

</details>

<details>
<summary>
14.  <b>How Virtual DOM works? </b>
</summary>

The _Virtual DOM_ works in three simple steps.

1. Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation.
2. Then the difference between the previous DOM representation and the new one is calculated.
3. Once the calculations are done, the real DOM will be updated with only the things that have actually changed.
</details>

<details>
<summary>
15.  <b>What is the difference between Shadow DOM and Virtual DOM? </b>
</summary>

The _Shadow DOM_ is a browser technology designed primarily for scoping variables and CSS in _web components_. The _Virtual DOM_ is a concept implemented by libraries in JavaScript on top of browser APIs.

</details>

<details>
<summary>
16.  <b>What is React Fiber? </b>
</summary>

Fiber is the new _reconciliation_ engine or reimplementation of core algorithm in React v16. The goal of React Fiber is to increase its suitability for areas like animation, layout, gestures, ability to pause, abort, or reuse work and assign priority to different types of updates; and new concurrency primitives.

</details>

<details>
<summary>
17.  <b>What is the main goal of React Fiber? </b>
</summary>

The goal of _React Fiber_ is to increase its suitability for areas like animation, layout, and gestures. Its headline feature is **incremental rendering**: the ability to split rendering work into chunks and spread it out over multiple frames.

Its main goals are:

1. Ability to split interruptible work in chunks.
2. Ability to prioritize, rebase and reuse work in progress.
3. Ability to yield back and forth between parents and children to support layout in React.
4. Ability to return multiple elements from render().
5. Better support for error boundaries.

</details>

<details>
<summary>
18.  <b>What are controlled components </b>
</summary>

A component that controls the input elements within the forms on subsequent user input is called **Controlled Component**, i.e, every state mutation will have an associated handler function. That means, the displayed data is always in sync with the state of the component.

The controlled components will be implemented using the below steps,

1. Initialize the state using use state hooks in function components or inside constructor for class components.
2. Set the value of the form element to the respective state variable.
3. Create an event handler to handle the user input changes through useState updater function or setState from class component.
4. Attach the above event handler to form elements change or click events

For example, the name input field updates the user name using `handleChange` event handler as below,

```javascript
import React, { useState } from "react";

function UserProfile() {
  const [username, setUsername] = useState("");

  const handleChange = (e) => {
    setUsername(e.target.value);
  };

  return (
    <form>
      <label>
        Name:
        <input type="text" value={username} onChange={handleChange} />
      </label>
    </form>
  );
}
```

</details>

<details>
<summary>
19.  <b> What are uncontrolled components?</b>
</summary>

The **Uncontrolled Components** are the ones that store their own state internally, and you query the DOM using a ref to find its current value when you need it. This is a bit more like traditional HTML.

The uncontrolled components will be implemented using the below steps,

1. Create a ref using useRef react hook in function component or `React.createRef()` in class based component.
2. Attach this ref to the form element.
3. The form element value can be accessed directly through `ref` in event handlers or `componentDidMount` for class components

In the below UserProfile component, the `username` input is accessed using ref.

```jsx harmony
import React, { useRef } from "react";

function UserProfile() {
  const usernameRef = useRef(null);

  const handleSubmit = (event) => {
    event.preventDefault();
    console.log("The submitted username is: " + usernameRef.current.value);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Username:
        <input type="text" ref={usernameRef} />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```

In most cases, it's recommend to use controlled components to implement forms. In a controlled component, form data is handled by a React component. The alternative is uncontrolled components, where form data is handled by the DOM itself.

<details><summary><b>See Class</b></summary>
    <p>

```jsx harmony
class UserProfile extends React.Component {
  constructor(props) {
    super(props);
    this.handleSubmit = this.handleSubmit.bind(this);
    this.input = React.createRef();
  }

  handleSubmit(event) {
    alert("A name was submitted: " + this.input.current.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          {"Name:"}
          <input type="text" ref={this.input} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

</p>
    </details>
</details>

<details>
<summary>
20.  <b> What is the difference between createElement and cloneElement? </b>
</summary>

- JSX elements will be transpiled to `React.createElement()` functions to create React elements which are going to be used for the object representation of UI.
- Whereas `cloneElement` is used to clone an element and pass it new props.

</details>

<details>
<summary>
21.  <b> What is Lifting State Up in React?</b>
</summary>

When several components need to share the same changing data then it is recommended to _lift the shared state up_ to their closest common ancestor. That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components.

</details>

<details>
<summary>
22.  <b>What are Higher-Order Components? </b>
</summary>

A _higher-order component_ (_HOC_) is a function that takes a component and returns a new component. Basically, it's a pattern that is derived from React's compositional nature.

We call them **pure components** because they can accept any dynamically provided child component but they won't modify or copy any behavior from their input components.

```javascript
const EnhancedComponent = higherOrderComponent(WrappedComponent);
```

HOC can be used for many use cases:

1. Code reuse, logic and bootstrap abstraction.
2. Render hijacking.
3. State abstraction and manipulation.
4. Props manipulation.
</details>

<details>
<summary>
23.  <b>What is children prop? </b>
</summary>

_Children_ is a prop that allows you to pass components as data to other components, just like any other prop you use. Component tree put between component's opening and closing tag will be passed to that component as `children` prop.

A simple usage of children prop looks as below,

```jsx harmony
    function MyDiv({ children }){
        return (
          <div>
            {children}
          </div>;
        );
    }

    export default function Greeting() {
      return (
        <MyDiv>
          <span>{"Hello"}</span>
          <span>{"World"}</span>
        </MyDiv>
      );
    }
```

<details><summary><b>See Class</b></summary>
<p>

```jsx harmony
const MyDiv = React.createClass({
  render: function () {
    return <div>{this.props.children}</div>;
  },
});

ReactDOM.render(
  <MyDiv>
    <span>{"Hello"}</span>
    <span>{"World"}</span>
  </MyDiv>,
  node
);
```

</p>
    </details>
</details>

<details>
<summary>
24.  <b>How to write comments in React </b>
</summary>

The comments in React/JSX are similar to JavaScript Multiline comments but are wrapped in curly braces.

**Single-line comments:**

```jsx harmony
<div>
  {/* Single-line comments(In vanilla JavaScript, the single-line comments are represented by double slash(//)) */}
  {`Welcome ${user}, let's play React`}
</div>
```

**Multi-line comments:**

```jsx harmony
<div>
  {/* Multi-line comments for more than
       one line */}
  {`Welcome ${user}, let's play React`}
</div>
```

</details>

<details>
<summary>
25.  <b>What is reconciliation? </b>
</summary>

`Reconciliation` is the process through which React updates the Browser DOM and makes React work faster. React use a `diffing algorithm` so that component updates are predictable and faster. React would first calculate the difference between the `real DOM` and the copy of DOM `(Virtual DOM)` when there's an update of components.

React stores a copy of Browser DOM which is called `Virtual DOM`. When we make changes or add data, React creates a new Virtual DOM and compares it with the previous one. This comparison is done by `Diffing Algorithm`.
Now React compares the Virtual DOM with Real DOM. It finds out the changed nodes and updates only the changed nodes in Real DOM leaving the rest nodes as it is. This process is called _Reconciliation_.

</details>

<details>
<summary>
26.  <b> Does the lazy function support named exports?</b>
</summary>

No, currently `React.lazy` function supports default exports only. If you would like to import modules which are named exports, you can create an intermediate module that reexports it as the default. It also ensures that tree shaking keeps working and don’t pull unused components.

Let's take a component file which exports multiple named components,

```javascript
    // MoreComponents.js
    export const SomeComponent = /* ... */;
    export const UnusedComponent = /* ... */;
```

and reexport `MoreComponents.js` components in an intermediate file `IntermediateComponent.js`

```javascript
// IntermediateComponent.js
export { SomeComponent as default } from "./MoreComponents.js";
```

    Now you can import the module using lazy function as below,

```javascript
import React, { lazy } from "react";
const SomeComponent = lazy(() => import("./IntermediateComponent.js"));
```

</details>

<details>
<summary>
27.  <b>Why React uses `className` over `class` attribute? </b>
</summary>

The attribute names written in JSX turned into keys of JavaScript objects and the JavaScript names cannot contain dashes or reversed words, it is recommended to use camelCase wherever applicable in JSX code. The attribute `class` is a keyword in JavaScript, and JSX is an extension of JavaScript. That's the principle reason why React uses `className` instead of `class`. Pass a string as the `className` prop.

```jsx harmony
    render() {
      return <span className="menu navigation-menu">{'Menu'}</span>
    }
```

</details>

<details>
<summary>
28.  <b>What are fragments? </b>
</summary>

It's a common pattern or practice in React for a component to return multiple elements. _Fragments_ let you group a list of children without adding extra nodes to the DOM.

You need to use either `<Fragment>` or a shorter syntax having empty tag (`<></>`).

Below is the example of how to use fragment inside _Story_ component.

```jsx harmony
function Story({ title, description, date }) {
  return (
    <Fragment>
      <h2>{title}</h2>
      <p>{description}</p>
      <p>{date}</p>
    </Fragment>
  );
}
```

It is also possible to render list of fragments inside a loop with the mandatory **key** attribute supplied.

```jsx harmony
function StoryBook() {
  return stories.map((story) => (
    <Fragment key={story.id}>
      <h2>{story.title}</h2>
      <p>{story.description}</p>
      <p>{story.date}</p>
    </Fragment>
  ));
}
```

Usually, you don't need to use `<Fragment>` until there is a need of _key_ attribute. The usage of shorter syntax looks like below.

```jsx harmony
function Story({ title, description, date }) {
  return (
    <>
      <h2>{title}</h2>
      <p>{description}</p>
      <p>{date}</p>
    </>
  );
}
```

</details>

<details>
<summary>
29.  <b>Why fragments are better than container divs? </b>
</summary>

Below are the list of reasons to prefer fragments over container DOM elements,

1. Fragments are a bit faster and use less memory by not creating an extra DOM node. This only has a real benefit on very large and deep trees.
2. Some CSS mechanisms like _Flexbox_ and _CSS Grid_ have a special parent-child relationships, and adding divs in the middle makes it hard to keep the desired layout.
3. The DOM Inspector is less cluttered.

</details>

<details>
<summary>
30.  <b>What are stateless components? </b>
</summary>

If the behaviour of a component is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless you need to use a lifecycle hook in your components, you should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the `this` keyword altogether.

</details>

<details>
<summary>
31.  <b>What are stateful components? </b>
</summary>

If the behaviour of a component is dependent on the _state_ of the component then it can be termed as stateful component. These _stateful components_ are either function components with hooks or _class components_.

Let's take an example of function stateful component which update the state based on click event,

```javascript
    import React, {useState} from 'react';

    const App = (props) => {
    const [count, setCount] = useState(0);
    handleIncrement() {
      setCount(count+1);
    }

    return (
      <>
        <button onClick={handleIncrement}>Increment</button>
        <span>Counter: {count}</span>
      </>
      )
    }
```

<details><summary><b>See Class</b></summary>
<p>
The equivalent class stateful component with a state that gets initialized in the `constructor`.

```jsx harmony
class App extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  handleIncrement() {
    setState({ count: this.state.count + 1 });
  }

  render() {
    <>
      <button onClick={() => this.handleIncrement}>Increment</button>
      <span>Count: {count}</span>
    </>;
  }
}
```

</p>
    </details>
</details>

<details>
<summary>
32.  <b>What are the advantages of React? </b>
</summary>

Below are the list of main advantages of React,

1. Increases the application's performance with _Virtual DOM_.
2. JSX makes code easy to read and write.
3. It renders both on client and server side (_SSR_).
4. Easy to integrate with frameworks (Angular, Backbone) since it is only a view library.
5. Easy to write unit and integration tests with tools such as Jest.
</details>

<details>
<summary>
33.  <b> What are the limitations of React</b>
</summary>
Apart from the advantages, there are few limitations of React too,

1. React is just a view library, not a full framework.
2. There is a learning curve for beginners who are new to web development.
3. Integrating React into a traditional MVC framework requires some additional configuration.
4. The code complexity increases with inline templating and JSX.
5. Too many smaller components leading to over engineering or boilerplate.
</details>

<details>
<summary>
34.  <b> What are the recommended ways for static type checking?</b>
</summary>

Normally we use _PropTypes library_ (`React.PropTypes` moved to a `prop-types` package since React v15.5) for _type checking_ in the React applications. For large code bases, it is recommended to use _static type checkers_ such as Flow or TypeScript, that perform type checking at compile time and provide auto-completion features.

</details>

<details>
<summary>
35.  <b>What is the use of `react-dom` package? </b>
</summary>

The `react-dom` package provides _DOM-specific methods_ that can be used at the top level of your app. Most of the components are not required to use this module. Some of the methods of this package are:

1. `render()`
2. `hydrate()`
3. `unmountComponentAtNode()`
4. `findDOMNode()`
5. `createPortal()`

</details>

<details>
<summary>
36.  <b>What is ReactDOMServer? </b>
</summary>

The `ReactDOMServer` object enables you to render components to static markup (typically used on node server). This object is mainly used for _server-side rendering_ (SSR). The following methods can be used in both the server and browser environments:

1. `renderToString()`
2. `renderToStaticMarkup()`

For example, you generally run a Node-based web server like Express, Hapi, or Koa, and you call `renderToString` to render your root component to a string, which you then send as response.

```javascript
// using Express
import { renderToString } from "react-dom/server";
import MyPage from "./MyPage";

app.get("/", (req, res) => {
  res.write("<!DOCTYPE html><html><head><title>My Page</title></head><body>");
  res.write('<div id="content">');
  res.write(renderToString(<MyPage />));
  res.write("</div></body></html>");
  res.end();
});
```

</details>

<details>
<summary>
37.  <b>How to use innerHTML in React? </b>
</summary>

The `dangerouslySetInnerHTML` attribute is React's replacement for using `innerHTML` in the browser DOM. Just like `innerHTML`, it is risky to use this attribute considering cross-site scripting (XSS) attacks. You just need to pass a `__html` object as key and HTML text as value.

In this example MyComponent uses `dangerouslySetInnerHTML` attribute for setting HTML markup:

```jsx harmony
function createMarkup() {
  return { __html: "First &middot; Second" };
}

function MyComponent() {
  return <div dangerouslySetInnerHTML={createMarkup()} />;
}
```

</details>

<details>
<summary>
38.  <b> How events are different in React? </b>
</summary>
Handling events in React elements has some syntactic differences:

1. React event handlers are named using camelCase, rather than lowercase.
2. With JSX you pass a function as the event handler, rather than a string.
</details>

<details>
<summary>
39.  <b> How do you conditionally render components? </b>
</summary>

In some cases you want to render different components depending on some state. JSX does not render `false` or `undefined`, so you can use conditional _short-circuiting_ to render a given part of your component only if a certain condition is true.

```jsx harmony
const MyComponent = ({ name, address }) => (
  <div>
    <h2>{name}</h2>
    {address && <p>{address}</p>}
  </div>
);
```

If you need an `if-else` condition then use _ternary operator_.

```jsx harmony
const MyComponent = ({ name, address }) => (
  <div>
    <h2>{name}</h2>
    {address ? <p>{address}</p> : <p>{"Address is not available"}</p>}
  </div>
);
```

</details>

<details>
<summary>
40.  <b>Why we need to be careful when spreading props on DOM elements?</b>
</summary>

When we _spread props_ we run into the risk of adding unknown HTML attributes, which is a bad practice. Instead we can use prop destructuring with `...rest` operator, so it will add only required props.

For example,

```jsx harmony
const ComponentA = () => (
  <ComponentB isDisplay={true} className={"componentStyle"} />
);

const ComponentB = ({ isDisplay, ...domProps }) => (
  <div {...domProps}>{"ComponentB"}</div>
);
```

</details>

<details>
<summary>
41.  <b>How do you memoize a component? </b>
</summary>

There are memoize libraries available which can be used on function components.

For example `moize` library can memoize the component in another component.

```jsx harmony
import moize from "moize";
import Component from "./components/Component"; // this module exports a non-memoized component

const MemoizedFoo = moize.react(Component);

const Consumer = () => {
  <div>
    {"I will memoize the following entry:"}
    <MemoizedFoo />
  </div>;
};
```

**Update:** Since React v16.6.0, we have a `React.memo`. It provides a higher order component which memoizes component unless the props change. To use it, simply wrap the component using React.memo before you use it.

```js
const MemoComponent = React.memo(function MemoComponent(props) {
  /* render using props */
});
OR;
export default React.memo(MyFunctionComponent);
```

</details>

<details>
<summary>
42.  <b>  How you implement Server Side Rendering or SSR?</b>
</summary>

React is already equipped to handle rendering on Node servers. A special version of the DOM renderer is available, which follows the same pattern as on the client side.

```jsx harmony
import ReactDOMServer from "react-dom/server";
import App from "./App";

ReactDOMServer.renderToString(<App />);
```

This method will output the regular HTML as a string, which can be then placed inside a page body as part of the server response. On the client side, React detects the pre-rendered content and seamlessly picks up where it left off.

</details>

<details>
<summary>
43.  <b>How to enable production mode in React? </b>
</summary>

You should use Webpack's `DefinePlugin` method to set `NODE_ENV` to `production`, by which it strip out things like propType validation and extra warnings. Apart from this, if you minify the code, for example, Uglify's dead-code elimination to strip out development only code and comments, it will drastically reduce the size of your bundle.

</details>

<details>
<summary>
44.  <b>Do Hooks replace render props and higher order components? </b>
</summary>

Both render props and higher-order components render only a single child but in most of the cases Hooks are a simpler way to serve this by reducing nesting in your tree.

</details>

<details>
<summary>
45.  <b>What are the Pointer Events supported in React? </b>
</summary>

_Pointer Events_ provide a unified way of handling all input events. In the old days we had a mouse and respective event listeners to handle them but nowadays we have many devices which don't correlate to having a mouse, like phones with touch surface or pens. We need to remember that these events will only work in browsers that support the _Pointer Events_ specification.

The following event types are now available in _React DOM_:

1. `onPointerDown`
2. `onPointerMove`
3. `onPointerUp`
4. `onPointerCancel`
5. `onGotPointerCapture`
6. `onLostPointerCapture`
7. `onPointerEnter`
8. `onPointerLeave`
9. `onPointerOver`
10. `onPointerOut`

</details>

<details>
<summary>
46.  <b>Why should component names start with capital letter? </b>
</summary>

If you are rendering your component using JSX, the name of that component has to begin with a capital letter otherwise React will throw an error as an unrecognized tag. This convention is because only HTML elements and SVG tags can begin with a lowercase letter.

```jsx harmony
    function SomeComponent {
      // Code goes here
    }
```

    You can define function component whose name starts with lowercase letter, but when it's imported it should have a capital letter. Here lowercase is fine:

```jsx harmony
    function myComponent {
      render() {
        return <div />;
      }
    }

    export default myComponent;
```

    While when imported in another file it should start with capital letter:

```jsx harmony
import MyComponent from "./myComponent";
```

</details>

<details>
<summary>
47.  <b> How to loop inside JSX? </b>
</summary>

You can simply use `Array.prototype.map` with ES6 _arrow function_ syntax.

For example, the `items` array of objects is mapped into an array of components:

```jsx harmony
<tbody>
  {items.map((item) => (
    <SomeComponent key={item.id} name={item.name} />
  ))}
</tbody>
```

But you can't iterate using `for` loop:

```jsx harmony
    <tbody>
      for (let i = 0; i < items.length; i++) {
        <SomeComponent key={items[i].id} name={items[i].name} />
      }
    </tbody>
```

This is because JSX tags are transpiled into _function calls_, and you can't use statements inside expressions. This may change thanks to `do` expressions which are _stage 1 proposal_.

</details>

<details>
<summary>
48.  <b> What is React proptype array with shape?</b>
</summary>

If you want to pass an array of objects to a component with a particular shape then use `React.PropTypes.shape()` as an argument to `React.PropTypes.arrayOf()`.

```javascript
ReactComponent.propTypes = {
  arrayWithShape: React.PropTypes.arrayOf(
    React.PropTypes.shape({
      color: React.PropTypes.string.isRequired,
      fontSize: React.PropTypes.number.isRequired,
    })
  ).isRequired,
};
```

</details>

<details>
<summary>
49.  <b>How to conditionally apply class attributes? </b>
</summary>

You shouldn't use curly braces inside quotes because it is going to be evaluated as a string.

```jsx harmony
    <div className="btn-panel {this.props.visible ? 'show' : 'hidden'}">
```

Instead you need to move curly braces outside (don't forget to include spaces between class names):

```jsx harmony
    <div className={'btn-panel ' + (this.props.visible ? 'show' : 'hidden')}>
```

_Template strings_ will also work:

```jsx harmony
    <div className={`btn-panel ${this.props.visible ? 'show' : 'hidden'}`}>
```

</details>

<details>
<summary>
50.  <b> What is the difference between React and ReactDOM?</b>
</summary>

The `react` package contains `React.createElement()`, `React.Component`, `React.Children`, and other helpers related to elements and component classes. You can think of these as the isomorphic or universal helpers that you need to build components. The `react-dom` package contains `ReactDOM.render()`, and in `react-dom/server` we have _server-side rendering_ support with `ReactDOMServer.renderToString()` and `ReactDOMServer.renderToStaticMarkup()`.

</details>

<details>
<summary>
51.  <b> </b>
</summary>
</details>

<details>
<summary>
52.  <b> </b>
</summary>
</details>

<details>
<summary>
53.  <b> </b>
</summary>
</details>

<details>
<summary>
54.  <b> </b>
</summary>
</details>
