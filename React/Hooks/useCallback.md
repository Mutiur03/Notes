
**Function version of useRef**
### Introduction 

The `useCallback` hook is used to memoize callback functions, preventing unnecessary re-creations on every render. It helps optimize performance, especially in child components that rely on reference equality.

### Syntax

```jsx
const memoizedCallback = useCallback(() => {
  // function logic
}, [dependencies]);
```

- The first argument is the function to be memoized.
- The second argument is an array of dependencies that trigger re-creation when changed.

### Use Cases

#### 1. Preventing Unnecessary Function Recreation

```jsx
import { useState, useCallback } from 'react';

function Button({ onClick }) {
  console.log('Button re-rendered');
  return <button onClick={onClick}>Click Me</button>;
}

function App() {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    setCount((prev) => prev + 1);
  }, []);

  return (
    <div>
      <p>Count: {count}</p>
      <Button onClick={handleClick} />
    </div>
  );
}
```

**Use Case:** Preventing `Button` from re-rendering when `handleClick` does not change.

#### 2. Optimizing Performance in Lists

```jsx
import { useState, useCallback } from 'react';

function List({ items, onItemClick }) {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index} onClick={() => onItemClick(item)}>{item}</li>
      ))}
    </ul>
  );
}

function App() {
  const [selectedItem, setSelectedItem] = useState(null);
  const items = ['Apple', 'Banana', 'Cherry'];

  const handleItemClick = useCallback((item) => {
    setSelectedItem(item);
  }, []);

  return (
    <div>
      <List items={items} onItemClick={handleItemClick} />
      <p>Selected: {selectedItem}</p>
    </div>
  );
}
```

**Use Case:** Avoiding function recreation on every render, reducing unnecessary re-renders in the list.

#### 3. Using useCallback with React.memo

```jsx
import { useState, useCallback, memo } from 'react';

const ChildComponent = memo(({ onClick }) => {
  console.log('ChildComponent rendered');
  return <button onClick={onClick}>Click</button>;
});

function ParentComponent() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount((prev) => prev + 1);
  }, []);

  return (
    <div>
      <p>Count: {count}</p>
      <ChildComponent onClick={increment} />
    </div>
  );
}
```

**Use Case:** Using `useCallback` with `React.memo` ensures that `ChildComponent` only re-renders when necessary.

### Conclusion

The `useCallback` hook is useful for optimizing performance by preventing unnecessary function re-creations. It is commonly used when passing functions to child components or handling event listeners.