### React Basics 

1. **What is React and why is it used?**
   - React is a JavaScript library for building user interfaces, especially for single-page applications. It allows developers to create reusable UI components that manage their own state, improving code reusability and performance.

2. **Explain the difference between functional and class components in React.**
   - Functional components are stateless, simpler, and primarily used for presentational purposes. Class components can manage state and lifecycle methods but have been largely replaced by functional components with Hooks, which add state and lifecycle functionality.

3. **What is JSX?**
   - JSX is a syntax extension for JavaScript that looks similar to HTML. It is used with React to describe UI components. JSX allows you to write HTML-like code in JavaScript that gets transpiled to React.createElement calls.

4. **How do you create a React component?**
   - A React component can be created as either a function or a class. For example, a functional component:
     ```js
     function MyComponent() {
       return <div>Hello, World!</div>;
     }
     ```

5. **What are props in React?**
   - Props (short for properties) are inputs passed into React components that allow data to be passed from one component to another.

6. **How do you pass data between components in React?**
  In React, data is passed from a parent component to a child component using **props** (short for properties). Props are a way to send data from one component to another, usually from a higher-level (parent) component to a lower-level (child) component. The child component receives these props as arguments and can use them to display or work with data.

### Example: Passing data from a parent to a child

1. **Parent Component:**

```jsx
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const message = "Hello from Parent!"; // Data to pass as props
  return (
    <div>
      <h1>Parent Component</h1>
      {/* Passing the message as a prop to ChildComponent */}
      <ChildComponent greeting={message} />
    </div>
  );
}

export default ParentComponent;
```

2. **Child Component:**

```jsx
import React from 'react';

function ChildComponent(props) {
  return (
    <div>
      <h2>Child Component</h2>
      {/* Accessing the passed prop using props.greeting */}
      <p>{props.greeting}</p>
    </div>
  );
}

export default ChildComponent;
```

### Explanation:
- In the `ParentComponent`, we define a string `message = "Hello from Parent!"` and pass it as a prop (`greeting`) to the `ChildComponent` using JSX syntax: `<ChildComponent greeting={message} />`.
- The `ChildComponent` receives the `greeting` prop through the `props` object. Inside the child component, we access this data using `props.greeting` and display it inside a `<p>` tag.

**Output:**
```
Parent Component
Hello from Parent!
```

In this example, data is passed from the `ParentComponent` to the `ChildComponent` via the `greeting` prop.

7. **What is the virtual DOM and how does it work?**
   - The virtual DOM is a lightweight copy of the real DOM that React uses to make updates more efficient. React compares the virtual DOM to the real DOM and only updates the parts of the DOM that have changed.

8. **Explain the component lifecycle in React.**
   - The component lifecycle includes three main phases: Mounting (when the component is added to the DOM), Updating (when it re-renders due to state or props changes), and Unmounting (when the component is removed from the DOM). Lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` allow developers to control behavior during these phases.

12. **How do you handle events in React?**
    - Event handling in React is done via JSX syntax. Events are written in camelCase (e.g., `onClick`) and can be handled by passing functions as event handlers.
      ```js
      <button onClick={handleClick}>Click Me</button>
      ```

13. **What is the purpose of fragments in React?**
    - Fragments allow grouping multiple elements without adding extra nodes to the DOM. They help prevent unnecessary nesting and improve performance.
      ```js
      <>
        <p>Element 1</p>
        <p>Element 2</p>
      </>
      ```


---

### Hooks 

1. **What are React Hooks?**
   - Hooks are functions that allow functional components to manage state and side effects, which was previously only possible with class components.

2. **Explain the useState Hook and provide an example.**
   - `useState` allows you to add state to functional components. Example:
     ```js
     const [count, setCount] = useState(0);
     ```

3. **What is the useEffect Hook used for?**
   - `useEffect` is used to manage side effects in functional components, like fetching data or setting up event listeners.

5. **What are the rules of Hooks?**
   - Hooks should only be called at the top level of functional components or custom hooks, not inside loops or conditionals. Hooks must only be called in React function components or custom hooks.

6. **How do you implement componentDidMount with useEffect?**
   - By passing an empty array as the second argument to `useEffect`, it runs only after the first render:
     ```js
     useEffect(() => {
       // Code to run once after the component mounts
     }, []);
     ```

---

### Redux 

1. **What is Redux and why might you use it in a React application?**
   - Redux is a state management library used for managing application state across components in a consistent and predictable way.

2. **Explain the core concepts of Redux: store, actions, and reducers.**
   - The **store** holds the state, **actions** describe state changes, and **reducers** handle how actions transform the state.

3. **What is the purpose of middleware in Redux?**
   - Middleware in Redux extends functionality, such as handling asynchronous actions or logging, between action dispatches and the reducer.

4. **How do you connect Redux to a React application?**
   - Use the `Provider` component to wrap your app and `connect` or `useSelector`/`useDispatch` hooks to connect components to the Redux store.

5. **Explain the concept of immutability in Redux.**
   - Redux requires state to be immutable, meaning you should never mutate state directly. Instead, always return a new state object.

6. **What is the Redux Thunk middleware used for?**
   - Redux Thunk allows you to write asynchronous logic that interacts with the Redux store, like making API calls before dispatching an action.

7. **How do you handle asynchronous actions in Redux?**
   - Use middleware like Redux Thunk to dispatch actions after asynchronous tasks like API requests complete.

8. **What are selectors in Redux and why are they useful?**
   - Selectors are functions used to retrieve specific data from the Redux store, improving code readability and reusability.

9. **Explain the concept of action creators in Redux.**
   - Action creators are functions that return action objects, encapsulating the process of creating actions.

10. **How does Redux differ from React's built-in state management?**
    - Redux manages the global state for the entire app, while React's built-in state (useState) is component-specific.

---

### JavaScript Basics 

1. **What is the difference between let, const, and var in JavaScript?**
   - `let` and `const` are block-scoped, while `var` is function-scoped. `const` is used for constants, while `let` allows reassignment.

2. **Explain closure in JavaScript.**
   - A closure occurs when a function retains access to variables in its outer scope, even after the outer function has returned.

3. **What is the difference between == and === in JavaScript?**
   - `==` checks for equality after type coercion, while `===` checks for strict equality without type coercion.

4. **How does the 'this' keyword work in JavaScript?**
   - `this` refers to the context in which a function is called. In objects, `this` refers to the object calling the function.


6. **What are arrow functions and how do they differ from regular functions?**
   - Arrow functions are a more concise syntax for functions and do not bind their own `this`, inheriting it from the parent context.

7. **What is the purpose of the async/await syntax in JavaScript?**
   - `async/await` allows you to write asynchronous code in a synchronous style, making promises easier to work with.

8. **Explain the concept of hoisting in JavaScript.**
   - Hoisting is JavaScript’s default behavior of moving variable and function declarations to the top of their scope before code execution.


10. **How does the spread operator (...) work in JavaScript?**
    - The spread operator expands arrays or objects into individual elements. For example:
      ```js
      const newArray = [...oldArray];
      ```
