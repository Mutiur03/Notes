### Introduction

The `useMemo` hook is used to optimize performance by memoizing the result of an expensive computation. It prevents unnecessary recalculations during renders.

### Syntax

```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(dependencies), [dependencies]);
```

- The first argument is a function that returns the computed value.
- The second argument is an array of dependencies that triggers recomputation when changed.

### Use Cases

#### 1. Optimizing Expensive Calculations

```jsx
import { useState, useMemo } from 'react';

function ExpensiveComponent({ num }) {
  const computeFactorial = (n) => {
    console.log('Calculating factorial...');
    return n <= 1 ? 1 : n * computeFactorial(n - 1);
  };

  const factorial = useMemo(() => computeFactorial(num), [num]);

  return <p>Factorial of {num} is {factorial}</p>;
}
```

**Use Case:** Avoiding redundant expensive calculations when the dependency (`num`) remains unchanged.

#### 2. Preventing Unnecessary Re-renders in Lists

```jsx
import { useState, useMemo } from 'react';

function List({ items, filter }) {
  const filteredItems = useMemo(() => {
    console.log('Filtering items...');
    return items.filter((item) => item.includes(filter));
  }, [items, filter]);

  return (
    <ul>
      {filteredItems.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}
```

**Use Case:** Ensuring that filtering only occurs when `items` or `filter` changes, not on every render.

#### 3. Memoizing a Computed Value in a Component

```jsx
import { useState, useMemo } from 'react';

function PriceCalculator({ price, taxRate }) {
  const totalPrice = useMemo(() => price + price * taxRate, [price, taxRate]);

  return <p>Total Price: ${totalPrice}</p>;
}
```

**Use Case:** Avoiding redundant recalculations of derived values.

### Conclusion

The `useMemo` hook enhances performance by caching computed values and recomputing only when dependencies change. It is especially useful for avoiding slow calculations in large applications.