## 🔰 Core React Fundamentals

1. JSX and React.createElement
2. Components: Functional vs. Class (stick with Functional in modern React)
3. Props and State
4. Event Handling in React
5. Conditional Rendering
6. Lists and Keys
7. Controlled vs. Uncontrolled Components
8. Forms and Input Management

### 1. JSX and React.createElement

**Note:** JSX is a syntax extension for JavaScript that looks similar to HTML. Under the hood, JSX gets compiled to `React.createElement` calls.

**Example:**

```jsx
const element = <h1>Hello, world!</h1>;
// Compiled to:
const element = React.createElement('h1', null, 'Hello, world!');
```

---

### 2. Components: Functional vs. Class

**Note:** Components let you split the UI into reusable pieces. Functional components are preferred in modern React.

**Example (Functional):**

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

**Example (Class):**

```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

---

### 3. Props and State

**Note:** Props are read-only inputs to components. State is mutable data maintained by the component.

**Example:**

```jsx
function Counter() {
  const [count, setCount] = React.useState(0);
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

---

### 4. Event Handling in React

**Note:** Events are handled using camelCase syntax. Functions are passed without parentheses.

**Example:**

```jsx
function Button() {
  function handleClick() {
    alert('Button clicked!');
  }
  return <button onClick={handleClick}>Click Me</button>;
}
```

---

### 5. Conditional Rendering

**Note:** React can conditionally render elements using JavaScript logic.

**Example:**

```jsx
function Greeting(props) {
  if (props.isLoggedIn) {
    return <h1>Welcome back!</h1>;
  }
  return <h1>Please sign up.</h1>;
}
```

---

### 6. Lists and Keys

**Note:** Use `.map()` to render lists. Keys help React identify which items changed.

**Example:**

```jsx
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {numbers.map((number) => (
        <li key={number.toString()}>{number}</li>
      ))}
    </ul>
  );
}
```

---

### 7. Controlled vs. Uncontrolled Components

**Note:** Controlled components have their form data managed by React state. Uncontrolled components use refs.

**Example (Controlled):**

```jsx
function NameForm() {
  const [value, setValue] = React.useState('');
  return (
    <input value={value} onChange={(e) => setValue(e.target.value)} />
  );
}
```

**Example (Uncontrolled):**

```jsx
function NameForm() {
  const inputRef = React.useRef();
  function handleSubmit() {
    alert(inputRef.current.value);
  }
  return (
    <>
      <input ref={inputRef} />
      <button onClick={handleSubmit}>Submit</button>
    </>
  );
}
```

---

### 8. Forms and Input Management

**Note:** Forms in React usually use controlled components to handle input changes.

**Example:**

```jsx
function LoginForm() {
  const [email, setEmail] = React.useState('');
  const [password, setPassword] = React.useState('');

  function handleSubmit(e) {
    e.preventDefault();
    console.log(email, password);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      <input
        type="password"
        value={password}
        onChange={(e) => setPassword(e.target.value)}
        placeholder="Password"
      />
      <button type="submit">Login</button>
    </form>
  );
}
```
## 🔰 Core React Fundamentals

1. JSX and React.createElement
2. Components: Functional vs. Class (stick with Functional in modern React)
3. Props and State
4. Event Handling in React
5. Conditional Rendering
6. Lists and Keys
7. Controlled vs. Uncontrolled Components
8. Forms and Input Management

### 1. JSX and React.createElement

**Note:** JSX is a syntax extension for JavaScript that looks similar to HTML. Under the hood, JSX gets compiled to `React.createElement` calls.

**Example:**

```jsx
const element = <h1>Hello, world!</h1>;
// Compiled to:
const element = React.createElement('h1', null, 'Hello, world!');
```

---

### 2. Components: Functional vs. Class

**Note:** Components let you split the UI into reusable pieces. Functional components are preferred in modern React.

**Example (Functional):**

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

**Example (Class):**

```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

---

### 3. Props and State

**Note:** Props are read-only inputs to components. State is mutable data maintained by the component.

**Example:**

```jsx
function Counter() {
  const [count, setCount] = React.useState(0);
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

---

### 4. Event Handling in React

**Note:** Events are handled using camelCase syntax. Functions are passed without parentheses.

**Example:**

```jsx
function Button() {
  function handleClick() {
    alert('Button clicked!');
  }
  return <button onClick={handleClick}>Click Me</button>;
}
```

---

### 5. Conditional Rendering

**Note:** React can conditionally render elements using JavaScript logic.

**Example:**

```jsx
function Greeting(props) {
  if (props.isLoggedIn) {
    return <h1>Welcome back!</h1>;
  }
  return <h1>Please sign up.</h1>;
}
```

---

### 6. Lists and Keys

**Note:** Use `.map()` to render lists. Keys help React identify which items changed.

**Example:**

```jsx
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {numbers.map((number) => (
        <li key={number.toString()}>{number}</li>
      ))}
    </ul>
  );
}
```

---

### 7. Controlled vs. Uncontrolled Components

**Note:** Controlled components have their form data managed by React state. Uncontrolled components use refs.

**Example (Controlled):**

```jsx
function NameForm() {
  const [value, setValue] = React.useState('');
  return (
    <input value={value} onChange={(e) => setValue(e.target.value)} />
  );
}
```

**Example (Uncontrolled):**

```jsx
function NameForm() {
  const inputRef = React.useRef();
  function handleSubmit() {
    alert(inputRef.current.value);
  }
  return (
    <>
      <input ref={inputRef} />
      <button onClick={handleSubmit}>Submit</button>
    </>
  );
}
```

---

### 8. Forms and Input Management

**Note:** Forms in React usually use controlled components to handle input changes.

**Example:**

```jsx
function LoginForm() {
  const [email, setEmail] = React.useState('');
  const [password, setPassword] = React.useState('');

  function handleSubmit(e) {
    e.preventDefault();
    console.log(email, password);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      <input
        type="password"
        value={password}
        onChange={(e) => setPassword(e.target.value)}
        placeholder="Password"
      />
      <button type="submit">Login</button>
    </form>
  );
}
```
