
## Introduction

JavaScript is a single-threaded language that executes code synchronously by default. However, for handling asynchronous operations like network requests, file reading, and timers, JavaScript provides **Promises** and **Async/Await** to write clean and efficient asynchronous code.

## Promises

A **Promise** is an object representing the eventual completion or failure of an asynchronous operation. It can be in one of three states:

1. **Pending**: Initial state, operation not yet completed.
2. **Fulfilled**: Operation completed successfully.
3. **Rejected**: Operation failed.

### Creating a Promise

```javascript
const myPromise = new Promise((resolve, reject) => {
    let success = true; // Simulating success or failure
    setTimeout(() => {
        if (success) {
            resolve("Operation Successful");
        } else {
            reject("Operation Failed");
        }
    }, 2000);
});
```

### Handling Promises

We use `.then()` for success and `.catch()` for handling errors:

```javascript
myPromise
    .then(response => {
        console.log(response); // Output: Operation Successful (after 2 seconds)
    })
    .catch(error => {
        console.error(error);
    });
```

We can also use `.finally()` to execute code regardless of success or failure:

```javascript
myPromise
    .finally(() => {
        console.log("Operation Completed");
    });
```

### Chaining Promises

Promises can be chained to handle multiple asynchronous operations sequentially:

```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error("Error fetching data:", error));
```

## Async/Await

`async` and `await` provide a more readable and cleaner way to handle asynchronous operations without chaining `.then()`.

### Defining an Async Function

An `async` function always returns a Promise.

```javascript
async function fetchData() {
    return "Data Fetched";
}

fetchData().then(console.log); // Output: Data Fetched
```

### Using Await

`await` is used inside an `async` function to wait for a Promise to resolve before proceeding.

```javascript
async function getData() {
    try {
        let response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error("Error fetching data:", error);
    }
}

getData();
```

### Error Handling in Async/Await

We use `try...catch` to handle errors gracefully:

```javascript
async function fetchWithErrorHandling() {
    try {
        let response = await fetch("invalid_url"); // This will throw an error
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error("Error occurred:", error);
    }
}

fetchWithErrorHandling();
```

## Comparing Promises and Async/Await

|Feature|Promises|Async/Await|
|---|---|---|
|Readability|Harder due to chaining|More readable and synchronous-like|
|Error Handling|`.catch()`|`try...catch` block|
|Use Case|Suitable for multiple parallel async tasks|Best for sequential async tasks|

## Conclusion

- **Promises** provide a structured way to handle asynchronous operations.
- **Async/Await** makes asynchronous code more readable and easier to manage.
- Use `try...catch` for proper error handling in `async/await`.
- Prefer `async/await` for cleaner code but use Promises when parallel execution is required.

Understanding these concepts helps in writing efficient and maintainable JavaScript applications.