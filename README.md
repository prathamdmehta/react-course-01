# React Fundamentals

This README covers the essential React concepts and topics, including examples, to help you brush up on your React knowledge.

---

## 1. Building User Interfaces with Components
React allows you to build UIs using reusable components, which are JavaScript functions or classes that return JSX.

### Key Points:
- Components can be **functional** or **class-based**.
- They make the UI modular and easy to maintain.

### Example:
```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

function App() {
  return (
    <div>
      <Greeting name="John" />
      <Greeting name="Jane" />
    </div>
  );
}
```

---

## 2. Using, Sharing & Outputting Data
React components accept data through **props** and manage internal data with **state**.

### Key Points:
- **Props**: Data passed from parent to child components (read-only).
- **State**: Internal data managed by a component (mutable).

### Example:
```jsx
function Counter({ initialCount }) {
  const [count, setCount] = React.useState(initialCount);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

function App() {
  return <Counter initialCount={0} />;
}
```

---

## 3. Handling User Events
React uses a declarative approach to handle events like clicks, inputs, and form submissions.

### Key Points:
- Events are camelCased (e.g., `onClick`, `onChange`).
- Use functions to define event handlers.

### Example:
```jsx
function ButtonClick() {
  const handleClick = () => {
    alert("Button was clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
}
```

---

## 4. Building Interactive UIs with State
React's **state** enables dynamic, interactive UIs that respond to user actions.

### Key Points:
- Use `useState` to declare state in functional components.
- State updates cause re-renders, enabling dynamic UI updates.

### Example:
```jsx
function Toggle() {
  const [isOn, setIsOn] = React.useState(false);

  return (
    <button onClick={() => setIsOn(!isOn)}>
      {isOn ? "ON" : "OFF"}
    </button>
  );
}
```
---

## 5. Virtual DOM, Fiber, and Reconciliation
React uses a **Virtual DOM** to improve performance and manage updates efficiently.

### **Virtual DOM**
- A lightweight representation of the real DOM.
- React calculates differences (diffing) between the virtual and real DOM to minimize updates.

### **Fiber**
- React's internal engine for efficient rendering and scheduling updates.

### **Reconciliation**
- React's process of updating the DOM to match the Virtual DOM.

#### Example:
```jsx
function App() {
  const [count, setCount] = React.useState(0);

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```
In this example, React efficiently updates only the `<h1>` element instead of re-rendering the entire DOM.

---
