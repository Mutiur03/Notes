
### Introduction

The `useReducer` hook is an alternative to `useState` for managing complex state logic in React components. It is particularly useful when state transitions depend on the previous state.

### Syntax

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

- `reducer`: A function that determines how the state changes based on the dispatched action.
- `initialState`: The initial value of the state.
- `dispatch`: A function used to send actions to the reducer.

### Use Cases

#### 1. Counter Example (Basic State Management)

```jsx
import { useReducer } from 'react';

const initialState = 0;
function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return state + 1;
    case 'decrement':
      return state - 1;
    case 'reset':
      return initialState;
    default:
      return state;
  }
}

function Counter() {
  const [count, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>Increment</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button>
      <button onClick={() => dispatch({ type: 'reset' })}>Reset</button>
    </div>
  );
}
```

**Use Case:** Managing numeric state with multiple actions.

#### 2. Managing Form State

```jsx
import { useReducer } from 'react';

const initialState = { name: '', email: '' };
function reducer(state, action) {
  return { ...state, [action.field]: action.value };
}

function Form() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <input
        type="text"
        placeholder="Name"
        value={state.name}
        onChange={(e) => dispatch({ field: 'name', value: e.target.value })}
      />
      <input
        type="email"
        placeholder="Email"
        value={state.email}
        onChange={(e) => dispatch({ field: 'email', value: e.target.value })}
      />
      <p>Name: {state.name}, Email: {state.email}</p>
    </div>
  );
}
```

**Use Case:** Managing complex forms where multiple fields update independently.

#### 3. Handling a Todo List

```jsx
import { useReducer } from 'react';

const initialState = [];
function reducer(state, action) {
  switch (action.type) {
    case 'add':
      return [...state, { id: Date.now(), text: action.text }];
    case 'remove':
      return state.filter((todo) => todo.id !== action.id);
    default:
      return state;
  }
}

function TodoApp() {
  const [todos, dispatch] = useReducer(reducer, initialState);
  const addTodo = () => {
    const text = prompt('Enter a todo:');
    dispatch({ type: 'add', text });
  };

  return (
    <div>
      <button onClick={addTodo}>Add Todo</button>
      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            {todo.text} <button onClick={() => dispatch({ type: 'remove', id: todo.id })}>Remove</button>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

**Use Case:** Managing lists and complex data structures.

### Conclusion

The `useReducer` hook is ideal for handling state with multiple sub-values and complex updates. It improves maintainability by centralizing state logic in a reducer function.