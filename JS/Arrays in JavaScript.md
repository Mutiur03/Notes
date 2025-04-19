## Creating an Array

You can create an array in JavaScript in several ways:

1. **Using an array literal:**
    
    ```js
    let fruits = ["Apple", "Banana", "Cherry"];
    ```
    
2. **Using the `new Array()` constructor:**
    
    ```js
    let numbers = new Array(1, 2, 3, 4, 5);
    ```
    
3. **Creating an array with different data types:**
    
    ```js
    let mixedArray = ["Hello", 42, true, {name: "John"}, [1, 2, 3], null, undefined, function() { return "Hello World"; }];
    ```
    

---

## Accessing Array Elements

Array elements are accessed using their index, which starts from **0**:

```js
let firstFruit = fruits[0]; // "Apple"
let secondNumber = numbers[1]; // 2
let objectInArray = mixedArray[3].name; // "John"
let functionResult = mixedArray[7](); // "Hello World"
```

---

## Modifying an Array

You can modify an array by assigning a new value to an index:

```js
fruits[1] = "Mango"; // Replaces "Banana" with "Mango"
```

---

## Common Array Methods

JavaScript provides several useful methods for manipulating arrays:

- **`push()`** – Adds an element to the end of an array.
    
    ```js
    fruits.push("Orange");
    ```
    
- **`pop()`** – Removes the last element from an array.
    
    ```js
    fruits.pop();
    ```
    
- **`shift()`** – Removes the first element from an array.
    
    ```js
    fruits.shift();
    ```
    
- **`unshift()`** – Adds an element to the beginning of an array.
    
    ```js
    fruits.unshift("Pineapple");
    ```
    
- **`splice()`** – Adds or removes elements at a specific index.
    
    ```js
    fruits.splice(1, 1); // Remove 1 element at index 1
    fruits.splice(1, 1, "Grapes"); // Replaces 1 element at index 1
    ```
    
- **`slice()`** – Returns a new array containing selected elements.
    
    ```js
    let citrus = fruits.slice(1, 3);
    ```
    
- **`concat()`** – Combines multiple arrays.
    
    ```js
    let allFruits = fruits.concat(["Kiwi", "Melon"]);
    ```
    
- **`indexOf()`** – Finds the index of an element.
    
    ```js
    let index = fruits.indexOf("Mango");
    ```
    
- **`includes()`** – Checks if an array contains an element.
    
    ```js
    let hasApple = fruits.includes("Apple");
    ```
    
- **`reverse()`** – Reverses the array order.
    
    ```js
    fruits.reverse();
    ```
    

---

## Iterating Over Arrays

### `for` Loop

```js
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

### `forEach()`

```js
fruits.forEach(fruit => console.log(fruit));
```

### `map()`

Creates a new array by applying a function to each element.

```js
let upperFruits = fruits.map(fruit => fruit.toUpperCase());
```

### `filter()`

Creates a new array with elements that match a condition.

```js
let filtered = numbers.filter(num => num > 2);
```

### `reduce()`

Reduces an array to a single value.

```js
let sum = numbers.reduce((acc, num) => acc + num, 0);
```

### `some()` and `every()`

- `some()` checks if at least one element satisfies a condition.
    
    ```js
    let hasBigNumber = numbers.some(num => num > 10);
    ```
    
- `every()` checks if all elements satisfy a condition.
    
    ```js
    let allPositive = numbers.every(num => num > 0);
    ```
    

---

## Array Properties

JavaScript arrays have several useful properties:

- **`length`** – Returns the number of elements in an array.
    
    ```js
    console.log(fruits.length); // Output: 3
    ```
    
- **`constructor`** – Returns the function that created the array.
    
    ```js
    console.log(fruits.constructor); // Output: function Array()
    ```
    
- **`prototype`** – Allows adding new properties and methods to arrays.
    
    ```js
    Array.prototype.customMethod = function() { console.log("Custom method"); };
    fruits.customMethod();
    ```
    

---

## Checking if a Variable is an Array

Use `Array.isArray()` to check if a variable is an array:

```js
console.log(Array.isArray(fruits)); // true
```

