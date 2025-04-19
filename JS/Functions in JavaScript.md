
Functions in JavaScript are blocks of reusable code that perform a specific task. They help make code more modular, readable, and maintainable.

### Declaring Functions

1. **Function Declaration:**

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Alice")); // Output: Hello, Alice!
```

1. **Function Expression:**

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};
console.log(greet("Bob")); // Output: Hello, Bob!
```

1. **Arrow Function (ES6+):**

```javascript
const greet = (name) => `Hello, ${name}!`;
console.log(greet("Charlie")); // Output: Hello, Charlie!
```

### Function Parameters and Default Values

```javascript
function greet(name = "Guest") {
    return `Hello, ${name}!`;
}
console.log(greet()); // Output: Hello, Guest!
```

### Anonymous Functions

Functions without a name are called anonymous functions, often used in callbacks.

```javascript
setTimeout(function() {
    console.log("This runs after 2 seconds");
}, 2000);
```

### Immediately Invoked Function Expressions (IIFE)

These functions execute immediately after being defined.

```javascript
(function() {
    console.log("IIFE executed!");
})();
```

### Higher-Order Functions

Functions that take other functions as arguments or return functions.

```javascript
function operate(a, b, operation) {
    return operation(a, b);
}
const add = (x, y) => x + y;
console.log(operate(5, 3, add)); // Output: 8
```
