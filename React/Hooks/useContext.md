### Introduction

The `useContext` hook allows function components to consume values from a React Context without using `Context.Consumer`. It simplifies state management and helps avoid prop drilling.

### Syntax

```jsx
const value = useContext(MyContext);
```

- `MyContext`: The context created with `React.createContext`.
- `value`: The current value of the context.

### Use Cases

#### 1. Basic Theme Context Example

```jsx
import { createContext, useContext } from 'react';

const ThemeContext = createContext('light');

function ThemedButton() {
  const theme = useContext(ThemeContext);
  return <button style={{ background: theme === 'dark' ? '#333' : '#fff' }}>Theme Button</button>;
}

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ThemedButton />
    </ThemeContext.Provider>
  );
}
```

**Use Case:** Passing theme values globally without prop drilling.

#### 2. Managing User Authentication

```jsx
import { createContext, useContext, useState } from 'react';

const AuthContext = createContext(null);

function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  return (
    <AuthContext.Provider value={{ user, setUser }}>
      {children}
    </AuthContext.Provider>
  );
}

function Profile() {
  const { user } = useContext(AuthContext);
  return <p>{user ? `Welcome, ${user.name}!` : 'Please log in.'}</p>;
}

function App() {
  return (
    <AuthProvider>
      <Profile />
    </AuthProvider>
  );
}
```

**Use Case:** Managing authentication state globally.

#### 3. Handling a Global Language Setting

```jsx
import { createContext, useContext } from 'react';

const LanguageContext = createContext('en');

function Greeting() {
  const language = useContext(LanguageContext);
  return <p>{language === 'en' ? 'Hello' : 'Hola'}</p>;
}

function App() {
  return (
    <LanguageContext.Provider value="es">
      <Greeting />
    </LanguageContext.Provider>
  );
}
```

**Use Case:** Setting and accessing language preferences.

### Conclusion

The `useContext` hook is a powerful way to manage global state without prop drilling. It is particularly useful for themes, authentication, and settings that multiple components need to access.