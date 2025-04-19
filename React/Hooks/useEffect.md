


`useEffect` is a React Hook that allows you to perform side effects in functional components. Side effects include data fetching, subscriptions, or manually changing the DOM.

## Syntax

The `useEffect` hook is imported from React and used within a functional component:

```jsx
import { useState, useEffect } from 'react';

function ExampleComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log(`Count updated: ${count}`);
  });

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### Explanation:

- `useEffect` runs after every render.
- The effect logs the updated count whenever the component re-renders.

## Different Formats of useEffect

### 1. **Run on Every Render (No Dependency Array)**

When no dependency array is provided, `useEffect` runs after every render.

```jsx
useEffect(() => {
  console.log("Component re-rendered");
});
```

### 2. **Run Only Once (Empty Dependency Array)**

To run the effect only once (e.g., fetching data on mount), use an empty dependency array `[]`.

```jsx
useEffect(() => {
  console.log("Component mounted");
}, []);
```

### 3. **Run on Specific State Change**

To run an effect only when a specific state changes, pass that state variable in the dependency array.

```jsx
useEffect(() => {
  console.log(`Count changed: ${count}`);
}, [count]);
```

This effect runs only when `count` changes.

### 4. **Cleanup Function (Component Unmounting & Effect Cleanup)**

`useEffect` can return a cleanup function to handle component unmounting or prevent memory leaks.

```jsx
useEffect(() => {
  const timer = setInterval(() => {
    console.log("Running interval");
  }, 1000);

  return () => {
    clearInterval(timer);
    console.log("Cleanup interval");
  };
}, []);
```

### 5. **Fetching Data Inside useEffect**

Using `useEffect` to fetch data from an API.

```jsx
useEffect(() => {
  async function fetchData() {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  }
  fetchData();
}, []);
```

## Best Practices

- **Always clean up effects** (e.g., remove event listeners, clear intervals).
- **Use dependencies wisely** to avoid unnecessary re-renders.
- **Use empty dependency array `[]` for running only on mount.**
- **Avoid infinite loops** by ensuring the dependency array does not include functions or objects that change on every render.


## Use Cases

#### 1. Running an Effect on Component Mount

```jsx
import { useEffect } from 'react';

function Welcome() {
  useEffect(() => {
    console.log('Component mounted!');
  }, []);

  return <h1>Welcome!</h1>;
}
```

**Use Case:** Running code once when the component mounts.

#### 2. Fetching Data from an API

```jsx
import { useState, useEffect } from 'react';

function DataFetcher() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/posts/1')
      .then(response => response.json())
      .then(json => setData(json));
  }, []);

  return <pre>{JSON.stringify(data, null, 2)}</pre>;
}
```

**Use Case:** Fetching external data when the component mounts.

#### 3. Updating the Title Dynamically

```jsx
import { useState, useEffect } from 'react';

function TitleUpdater() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return <button onClick={() => setCount(count + 1)}>Increment</button>;
}
```

**Use Case:** Updating the document title based on state changes.

#### 4. Setting Up an Interval

```jsx
import { useState, useEffect } from 'react';

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds(s => s + 1);
    }, 1000);
    
    return () => clearInterval(interval);
  }, []);

  return <p>Timer: {seconds}s</p>;
}
```

**Use Case:** Running a repeated action (e.g., a timer) and cleaning up on unmount.

#### 5. Cleaning Up Event Listeners

```jsx
import { useEffect } from 'react';

function WindowResizer() {
  useEffect(() => {
    const handleResize = () => console.log(window.innerWidth);
    window.addEventListener('resize', handleResize);

    return () => {
      window.removeEventListener('resize', handleResize);
    };
  }, []);

  return <p>Resize the window to see logs in the console.</p>;
}
```

**Use Case:** Attaching and detaching event listeners.

### Conclusion

The `useEffect` hook is essential for handling side effects in React applications. It helps manage data fetching, subscriptions, and interactions with external systems while ensuring proper cleanup to prevent memory leaks.