## React Hooks

### 1. useState

**Note:** `useState` lets you add state to functional components.

**Example:**

```jsx
function Counter() {
  const [count, setCount] = React.useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

---

### 2. useEffect

**Note:** `useEffect` lets you perform side effects in functional components.

**Example:**

```jsx
function Timer() {
  const [seconds, setSeconds] = React.useState(0);

  React.useEffect(() => {
    const interval = setInterval(() => {
      setSeconds((prev) => prev + 1);
    }, 1000);
    return () => clearInterval(interval);
  }, []);

  return <p>Seconds: {seconds}</p>;
}
```

---

### 3. useContext

**Note:** `useContext` allows you to consume context values directly without using `Context.Consumer`.

**Example:**

```jsx
const ThemeContext = React.createContext('light');

function ThemedComponent() {
  const theme = React.useContext(ThemeContext);
  return <div>Current theme: {theme}</div>;
}
```

---

### 4. useRef

**Note:** `useRef` provides a way to access and persist mutable values across renders, often used for DOM access.

**Example:**

```jsx
function FocusInput() {
  const inputRef = React.useRef(null);

  function handleClick() {
    inputRef.current.focus();
  }

  return (
    <>
      <input ref={inputRef} />
      <button onClick={handleClick}>Focus Input</button>
    </>
  );
}
```

---

### 5. useMemo

**Note:** `useMemo` memorizes the result of a computation to avoid expensive recalculations.

**Example:**

```jsx
function ExpensiveCalculation({ num }) {
  const result = React.useMemo(() => {
    console.log('Calculating...');
    return num * 2;
  }, [num]);

  return <div>Result: {result}</div>;
}
```

---

### 6. useCallback

**Note:** `useCallback` memorizes a function so it doesn’t get re-created unless its dependencies change.

**Example:**

```jsx
function Button({ onClick }) {
  return <button onClick={onClick}>Click me</button>;
}

function Parent() {
  const [count, setCount] = React.useState(0);
  const handleClick = React.useCallback(() => setCount(c => c + 1), []);

  return <Button onClick={handleClick} />;
}
```

---

### 7. Custom Hooks

**Note:** You can build your own hooks to extract reusable logic from components.

**Example:**

```jsx
function useWindowWidth() {
  const [width, setWidth] = React.useState(window.innerWidth);

  React.useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener('resize', handleResize);
    return () => window.removeEventListener('resize', handleResize);
  }, []);

  return width;
}

function DisplayWidth() {
  const width = useWindowWidth();
  return <p>Window width: {width}</p>;
}
```

---

### 8. useReducer

**Note:** `useReducer` is a more powerful alternative to `useState` for complex state logic.

**Example:**

```jsx
function reducer(state, action) {
  switch (action.type) {
    case 'increment': return { count: state.count + 1 };
    case 'decrement': return { count: state.count - 1 };
    default: return state;
  }
}

function Counter() {
  const [state, dispatch] = React.useReducer(reducer, { count: 0 });

  return (
    <>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
    </>
  );
}
```
