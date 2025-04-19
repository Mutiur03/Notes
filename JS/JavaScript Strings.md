### 1. Introduction

A string in JavaScript is a sequence of characters used to represent text. Strings are immutable and can be enclosed in single (`'`), double (`"`), or backticks (`` ` ``) for template literals.

### 2. Creating Strings

```javascript
let str1 = "Hello"; // Double quotes
let str2 = 'World'; // Single quotes
let str3 = `Hello, ${str2}!`; // Template literal
```

### 3. String Properties and Methods

#### **3.1 String Length**

```javascript
let text = "JavaScript";
console.log(text.length); // 10
```

#### **3.2 Accessing Characters**

```javascript
console.log(text[0]); // "J"
console.log(text.charAt(1)); // "a"
```

#### **3.3 String Methods**

|Method|Description|
|---|---|
|`toUpperCase()`|Converts string to uppercase|
|`toLowerCase()`|Converts string to lowercase|
|`trim()`|Removes whitespace from both ends|
|`slice(start, end)`|Extracts part of a string|
|`substring(start, end)`|Extracts characters between indexes|
|`replace(old, new)`|Replaces part of a string|
|`split(separator)`|Splits string into an array|

Example:

```javascript
let sentence = " JavaScript is fun! ";
console.log(sentence.toUpperCase()); // " JAVASCRIPT IS FUN! "
console.log(sentence.trim()); // "JavaScript is fun!"
console.log(sentence.slice(0, 10)); // "JavaScript"
```

### 4. String Concatenation

```javascript
let first = "Hello";
let second = "World";
let result = first + " " + second; // "Hello World"
```

Using `concat()`:

```javascript
console.log(first.concat(" ", second)); // "Hello World"
```

### 5. Template Literals

Template literals allow embedding expressions inside strings.

```javascript
let name = "Alice";
console.log(`Hello, ${name}!`); // "Hello, Alice!"
```

### 6. Escape Characters

Use `\` for special characters.

```javascript
console.log("He said, \"JavaScript is awesome!\"");
// Output: He said, "JavaScript is awesome!"
```

### 7. Searching in Strings

#### **7.1 `indexOf()`**

Finds the first occurrence of a substring.

```javascript
console.log("Hello World".indexOf("World")); // 6
```

#### **7.2 `includes()`**

Checks if a string contains a substring.

```javascript
console.log("Hello World".includes("World")); // true
```

#### **7.3 `startsWith()` and `endsWith()`**

```javascript
console.log("JavaScript".startsWith("Java")); // true
console.log("JavaScript".endsWith("Script")); // true
```

### 8. String Comparison

```javascript
console.log("apple" === "Apple"); // false (case-sensitive)
console.log("banana" > "apple"); // true (lexicographical order)
```

### 9. Summary

- Strings are immutable.
- Use single, double, or template literals.
- Various built-in methods help manipulate strings.
- Template literals allow embedding expressions.
- String comparison follows lexicographical order.

JavaScript provides powerful string manipulation capabilities, making text handling easy and efficient.