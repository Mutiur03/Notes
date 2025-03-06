
### **1. forEach() Method**

The `forEach()` method executes a provided function once for each array element. Unlike `map()`, it does not return a new array; instead, it modifies the original array if needed.

#### **Example 1: Modifying an array using forEach()**

```javascript
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];

function double(element, index, array) {
    array[index] = element * 2;
}

numbers.forEach(double);
numbers.forEach((element) => console.log(element));
```

**Explanation:**

- The `double` function multiplies each element by 2 and updates the original array.
- The modified array is then displayed using another `forEach()` call.

#### **Example 2: Converting Strings to Uppercase**

```javascript
let fruits = ["aam", "jam", "kathal", "Kola", "Lichu"];
function toUpperCase(element, i, array) {
    array[i] = element.toUpperCase();
}
fruits.forEach(toUpperCase);
console.log(fruits);
```

**Explanation:**

- Each fruit name is converted to uppercase using `toUpperCase()`.
- The `forEach()` method modifies the original `fruits` array.

### **2. map() Method**

The `map()` method creates a new array by applying a function to each element of the original array without modifying it.

#### **Example 1: Squaring Numbers**

```javascript
function square(element) {
    return Math.pow(element, 2);
}
let squaredNumbers = numbers.map(square);
console.log(squaredNumbers);
```

**Explanation:**

- The `map()` method applies the `square` function to each element and returns a new array.
- The original `numbers` array remains unchanged.

#### **Example 2: Formatting Dates**

```javascript
let dates = ["2024-12-25", "2022-12-11"];
function formatDate(element) {
    let part = element.split("-");
    return `${part[2]}-${part[1]}-${part[0]}`;
}
console.log(dates.map(formatDate));
```

**Explanation:**

- Each date is reformatted from `YYYY-MM-DD` to `DD-MM-YYYY` using `map()`.
- The original `dates` array remains unchanged.

### **3. filter() Method**

The `filter()` method creates a new array with elements that satisfy a given condition.

#### **Example: Filtering Adults from an Age List**

```javascript
let ages = [18, 55, 55, 6, 58, 25, 45, 4, 12, 56];
function isAdult(element) {
    return element >= 18;
}
let adults = ages.filter(isAdult);
console.log(adults);
```

**Explanation:**

- The `filter()` method returns a new array containing only values `>= 18`.

### **4. reduce() Method**

The `reduce()` method processes an array to return a single value, such as a sum or maximum value.

#### **Example 1: Calculating the Sum**

```javascript
const prices = [5, 10, 15, 20, 25, 30];
const total = prices.reduce(sum);
function sum(accumulator, element) {
    return accumulator + element;
}
console.log(total);
```

**Explanation:**

- `reduce()` iterates over `prices`, summing the values.
- The `accumulator` stores the intermediate sum.

#### **Example 2: Finding the Maximum Value**

```javascript
const maxValue = prices.reduce(max);
function max(accumulator, element) {
    return Math.max(accumulator, element);
}
console.log(maxValue);
```

**Explanation:**

- The function `max()` returns the larger value between `accumulator` and `element`.
- The final result is the highest value in the array.

### **Additional Examples Using map(), filter(), and reduce()**

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];

const squares = numbers.map((element) => Math.pow(element, 2));
console.log(...squares);

const cubes = numbers.map((element) => Math.pow(element, 3));
console.log(...cubes);

const evenNumbers = numbers.filter((element) => element % 2 === 0);
console.log(...evenNumbers);

const oddNumbers = numbers.filter((element) => element % 2 !== 0);
console.log(...oddNumbers);

const totalSum = numbers.reduce((prev, next) => prev + next);
console.log(totalSum);
```

**Key Differences Between forEach and map:**

- `forEach()` modifies the original array, while `map()` returns a new array.
- `map()` is more suitable when transformation is required without altering the original data.

