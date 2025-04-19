### Introduction

The `useRef` hook provides a way to persist values across renders without causing re-renders. It is often used to reference DOM elements or store mutable values.

### Syntax

```jsx
const ref = useRef(initialValue);
```

- `initialValue`: The initial value assigned to the ref.
- `ref.current`: The current value of the reference.

### Use Cases

#### 1. Accessing a DOM Element

```jsx
import { useRef, useEffect } from 'react';

function InputFocus() {
  const inputRef = useRef(null);

  useEffect(() => {
    inputRef.current.focus();
  }, []);

  return <input ref={inputRef} type="text" placeholder="Auto-focused input" />;
}
```

**Use Case:** Automatically focusing an input field when the component mounts.

#### 2. Storing Previous State

```jsx
import { useState, useRef, useEffect } from 'react';

function PreviousStateTracker() {
  const [count, setCount] = useState(0);
  const prevCount = useRef(count);

  useEffect(() => {
    prevCount.current = count;
  }, [count]);

  return (
    <div>
      <p>Current: {count}</p>
      <p>Previous: {prevCount.current}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

**Use Case:** Keeping track of previous state values without causing re-renders.

#### 3. Storing Mutable Values Without Re-rendering

```jsx
import { useState, useRef } from 'react';

function Timer() {
  const [count, setCount] = useState(0);
  const intervalRef = useRef(null);

  const startTimer = () => {
    if (!intervalRef.current) {
      intervalRef.current = setInterval(() => {
        setCount((c) => c + 1);
      }, 1000);
    }
  };

  const stopTimer = () => {
    clearInterval(intervalRef.current);
    intervalRef.current = null;
  };

  return (
    <div>
      <p>Time: {count}s</p>
      <button onClick={startTimer}>Start</button>
      <button onClick={stopTimer}>Stop</button>
    </div>
  );
}
```

**Use Case:** Managing intervals or timeouts without triggering re-renders.

### Conclusion

The `useRef` hook is a powerful tool for interacting with DOM elements, tracking previous states, and storing mutable values without causing re-renders. It is particularly useful for performance optimizations in React applications.