### 1. Alerts and Prompts

```javascript
// Display an alert box
alert("Hello!");
// Another way to show an alert
window.alert("Welcome to my website");
// Write content to the document
document.write("Hello, world!", "<hr>");

// Prompt the user for input
let a = prompt("Enter first number:");
let b = prompt("Enter second number:");

// Convert input to integers
a = parseInt(a);
b = parseInt(b);

// Display the sum
document.write("Sum: " + (a + b));
```

### 2. Variables and Data Types

```javascript
// Declare a variable
let age = 21;
// Print age using template literals
console.log(`You are ${age} years old`);
// Print the type of age
console.log(typeof age);
// Print age type using template literals
console.log(`Age is a ${typeof age}`);
```

### DOM Manipulation
```js
let nam = "Mutiur";
document.getElementById("myid").textContent = `Your name is ${nam}`;
```

## Function with User Input
```js
function run() {
    let username;
    username = document.getElementById("user").value;
    document.getElementById("user1").textContent = `Hey ${username}`;
}
```
## Type Conversion
```js
let x = 1;
let a = Number(x);
let b = String(x);
let c = Boolean(x);
```
### 3. String Manipulation

```javascript
let username = " Mutiur Rahman";
// Get character at index 0
console.log(username.charAt(0));
// Find the first occurrence of 'u'
console.log(username.indexOf("u"));
// Find the last occurrence of 'u'
console.log(username.lastIndexOf("u"));
// Get string length
console.log(username.length);

// Remove extra spaces
username = username.trim();
// Convert to lowercase
console.log(username.toLowerCase());
// Convert to uppercase
console.log(username.toUpperCase());
// Repeat string 3 times
console.log(username.repeat(3));
// Replace all spaces with empty string
console.log(username.replaceAll(" ", ""));
// Check if string starts with this
console.log(username.startsWith(" "));
// Pads insert spaces at the beginning
console.log(username.padStart(25," "));
// Pads insert spaces at the end
console.log(username.padEnd(25," "));
```

```js
//Validating Email
function isValidEmail(email) {
    return email.includes("@");
}
console.log(isValidEmail("mutiur5bb@gmail.com"));
```

```js
//Usecase
let email="mutiur5bb@gmail.com";
let user=email.slice(0, email.indexOf("@"));
let domain=email.slice(email.indexOf("@")+1);
console.log(user);
console.log(domain);
```
[[JavaScript Strings]]
### 4. Math Operations

```javascript
let x = 1;
// Round a number
let z = Math.round(x);
// Truncate decimal part
z = Math.trunc(x);
// Logarithm of x
z = Math.log(x);
// Trigonometric functions
z = Math.sin(x);
z = Math.cos(x);
z = Math.tan(x);
// Check if number is positive, negative or zero
z = Math.sign(x);

// Find max and min numbers
let max = Math.max(1, 2, 1, 4, 5);
let min = Math.min(1, 6, 5, 66, 3, 6, 5);

// Generate random number between 1 and 6
let random = Math.random();
random = Math.random() * 6;  // random number between 0 and 6
random = Math.floor(Math.random() * 6);  // random integer between 0 and 5
random = Math.floor(Math.random() * 6 + 1);  // random integer between 1 and 6
```

## Mathematical Operations
```js
let n = 3;
let m = n;
m **= 2; //m^2
console.log(n ** n * n);  //n**n = n^n //=81
console.log(m); //=9
```

### 5. Conditionals and Loops

```javascript
let isLoggedIn = false;
let username = "Mutiur03";
let password = "Mutiur03717";
let user, pass;

// Keep prompting user until valid credentials are entered
while (!isLoggedIn) {
    user = window.prompt("Enter your username");
    pass = window.prompt("Enter your password");
    if (user === username && pass === password) {
        alert("You are logged in");
        isLoggedIn = true;
    } else {
        alert("Invalid Credentials");
    }
}
```

### 6. Functions and Callbacks

```javascript
// Function that takes another function as a parameter
// we use this to ensure that any function will be called after execeting specifix function
function greet(callback) {
    console.log("Hello");
    callback();
}

// Callback function
function farewell() {
    console.log("Goodbye");
}

// Call greet function and pass farewell as a callback
greet(farewell);
```

### 7. Arrays and Spread Operators

```javascript
let numbers = [1, 2, 3, 3, 4, 5, 6, 7, 5, 6];
// Find max and min using spread operator
let max = Math.max(...numbers);
let min = Math.min(...numbers);
console.log(max, min);
// Spreading a String into an Array
let username = "Mutiur03";
console.log([...username].join("-"));
// Merging Arrays Using Spread Operator
let fruits = ["Am", "Jam", "Kathal", "Kola"];
let fav = ["Burger", "Pizza", "Fried", "Chicken"];
console.log(...fav);
let join = [...fruits, ...fav, "vgsfd", "gjd"];
console.log(...join);
console.log(join);
// Using Rest Operator in Function Parameters
// Converts in array
function fridgee(...bal) {
  console.log(bal);   
}
function get(...bal) {
  return bal;
}
let arr1 = "av";
let arr2 = "ad";
let arr3 = "asd";
let arr4 = "ffg";
let arr5 = "adf";
fridgee(arr1, arr2, arr3, arr4, arr5);
let fooo = get(arr1, arr2, arr3, arr4, arr5);
console.log(fooo);
// Summing Numbers Using Rest Operator
function sum(...params) {
  let result = 0;
  for (let num of params) {
    result += num;
  }
  return result;
}
let total = sum(1, 2, 4, 6, 4, 8, 3, 1, 5, 6, 3, 1, 2, 55, 5);
console.log(total);
// Combining Strings Using Rest Operator
function combine(...string) {
  return string.join(" ");
}
let add = combine("Engr.", "Mutiur", "Rahman");
console.log(add);
```

### 8. JavaScript Array Methods

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
//forEach changes main array but  others not
//The key diff between for each and map is, map doesn't changes the main variables value but forEach does.
// Double each element
numbers.forEach((element, index, array) => {array[index] = element * 2;});
console.log(...numbers)
// Square each element
const squared = numbers.map((element) => Math.pow(element, 2));
console.log(...squared);
// Filter even numbers
const evens = numbers.filter((element) => element % 2 === 0);
console.log(...evens);
// Reduce array to sum
const sum = numbers.reduce((prev, next) => prev + next);
console.log(sum);
```
[[Arrays in JavaScript]]
[[JavaScript Array Methods - forEach map filter and reduce]]

### 9. Objects and Methods

```javascript
const person1 = {
    firstName: `Mutiur`,
    age: 21,
    // Regular function (can use 'this')
    sayHello: function () { console.log(`Hello, ${this.firstName}`); },
    // Arrow function (cannot use 'this')
    sayGoodbye: () => console.log(`Goodbye, ${person1.firstName}`),
};
console.log(person1.firstName);
person1.sayHello();
person1.sayGoodbye();
```
[[OOP in JavaScript]]

### THIS 
```js
const obj = {
    name: "Alice",
    greet: function() {
        console.log("Hello, " + this.name);
    }
};
obj.greet(); // Hello, Alice
```

### Constructors 
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
}
const person1 = new Person("Bob", 25);
console.log(person1.name); // Bob
```


### Classes 
```js
class Animal {
  constructor(type) {
    this.type = type;
  }
  speak() {
    console.log(`A ${this.type} makes a sound.`);
  }
  price(pp) {
    return pp; // so we can also pass parameter only on function
  }
}
const dog = new Animal("Dog");
console.log(dog.price(25)); // A Dog makes a sound
```


### STATIC keyword 
Defines methods that belong to the class rather than instances.
```js
class MathUtils {
    static add(a, b) {
        return a + b;
    }
}
console.log(MathUtils.add(3, 4)); // 7 // no need to declare any varibale
```


### Inheritance 

```js
class Parent {
    constructor(name) {
        this.name = name;
    }
}
class Child extends Parent {
    greet() {
        console.log(`Hello, my name is ${this.name}`);
    }
}
const child = new Child("Charlie");
child.greet(); // Hello, my name is Charlie
```

### SUPER keyword 
```js
class Animal {
    constructor(name) {
        this.name = name;
    }
}
class Dog extends Animal {
    constructor(name, breed) {
        super(name);
        this.breed = breed;
    }
}
const myDog = new Dog("Buddy", "Golden Retriever");
console.log(myDog.name); // Buddy
```


### Getters & Setters 

```js
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
  set height(newHeight){ //func name should be same as variable
    if(newHeight>0){
        this._height=newHeight;  //_height for private element
    }
    else{
        console.error(`Enter a valid height`)
    }
  }
  get area() {
    return this._width * this._height;
  }
}
const rect = new Rectangle(5, -10);
console.log(rect.area); // 50
```

### Destructuring
Extract values from objects or arrays easily.

**Object Destructuring**
With object destructuring, you can assign properties of an object to variables with matching names.

```javascript
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Destructuring
let { firstName, lastName } = person;
```

In this example, the variables `firstName` and `lastName` are assigned the corresponding values from the `person` object. Notably, the order of properties does not matter in object destructuring. 

**Default Values**
If a property is absent in the object, you can assign a default value during destructuring.

```javascript
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Destructuring with default value
let { firstName, lastName, country = "US" } = person;
```

Here, `country` is assigned the default value "US" since it's not a property of the `person` object.

**Property Aliases**
You can also assign properties to variables with different names using aliases.

```javascript
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Destructuring with alias
let { lastName: surname } = person;
```

In this case, the `lastName` property is assigned to the variable `surname`. 

**Array Destructuring**
Destructuring can also be applied to arrays, allowing for the assignment of array elements to variables.

```javascript
// Create an Array
const fruits = ["Banana", "Orange", "Apple", "Mango"];

// Destructuring
let [fruit1, fruit2] = fruits;
```

Here, `fruit1` is assigned "Banana" and `fruit2` is assigned "Orange".

we can also use spread operator
```js
const colors = [" red", "blue", "black", "white","green"];
const [firstcolor, secondcolor, thirdcolor, ...extracolors] = colors;
console.log(firstcolor);
console.log(secondcolor);
console.log(thirdcolor);
console.log(extracolors);
```


### Nested objects 📫
Objects within objects.
```js
const company = {
    name: "TechCorp",
    location: {
        city: "New York",
        country: "USA"
    }
};
console.log(company.location.city); // New York
```


### Arrays of objects 
List of objects stored in an array.
```js
const students = [
    { name: "John", grade: "A" },{ name: "Jane", grade: "B" }
];
console.log(students[0].name); // John
students.push({ name: "Ami", grade: "A+" });
students.pop() //also all properties of array
```

### Sorting an array
```js
const numbers = [5, 3, 8, 1, 2];
numbers.sort((a, b) => a - b);
console.log("Sorted:", numbers); // [1, 2, 3, 5, 8]
```

```js
user=[{name:"Mutiur",age:21},{name:"Shumu",age:20}];
user.sort((a,b)=>a.age-b.age);
console.log(user);
user.sort((a,b)=>a.name.localeCompare(b.name));
console.log(user);
```

### Shuffle an array
```js
function shuffle(array) {
    for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
    }
}
shuffle(numbers);
console.log("Shuffled:", numbers);
```

### Dates
```js
const now = new Date();
console.log("Current Date:", now);
```

```js
date =new Date();
year = date.getFullYear();
month= date.getMonth();
day = date.getDate();
hour= date.getHours();
minutes= date.getMinutes();
seconds= date.getSeconds();
dayOfWeek = date.getDay();
console. log(year);
console. log(month) ;
console. log(day);
console. log(hour);
console. log(minutes);
console. log(seconds);
```

### Closures
A function defined inside of another function, the inner function has access to the variables and scope of the outer function. Allow for private variables and state maintenance Used frequently in JS frameworks: React, Vue, Angular
```js
function createCounter() {
    let count = 0;
    return function () {
        count++;
        return count;
    };
}
const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
```

### setTimeout
```js
setTimeout(() => {
    console.log("This runs after 2 seconds");
}, 2000);
```
### Clear Timeout
```js
let timeoutID = setTimeout(() => {
  console.log("This runs after 2 seconds");
}, 2000);
clearTimeout(timeoutID);
timeoutID=null;
```











































### 10. Password Generator Function

```javascript
function generatePassword(length, hasUpperCase, hasLowerCase, hasNumbers, hasSymbols) {
    let upperCase = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    let lowerCase = "abcdefghijklmnopqrstuvwxyz";
    let numbers = "0123456789";
    let symbols = "!@#$%^&*()[]{}";
    let characters = "";

    // Include character types if selected
    characters += hasUpperCase ? upperCase : "";
    characters += hasLowerCase ? lowerCase : "";
    characters += hasNumbers ? numbers : "";
    characters += hasSymbols ? symbols : "";

    if (characters.length < 1) {
        console.log("You must select at least one character type");
        return "";
    }
    if (length < 8) {
        console.log("Password length must be at least 8");
        return "";
    }

    let password = "";
    for (let i = 0; i < length; i++) {
        let index = Math.floor(Math.random() * characters.length);
        password += characters[index];
    }
    console.log(password);
}

// Generate an 8-character password with all character types
generatePassword(8, true, true, true, true);
```

### 11. Dice Rolling Simulation

```javascript
function rollDice() {
    let values = [];
    let num = document.getElementById("num").value;
    let results = document.getElementById("result");
    
    // Generate random dice values
    for (let i = 0; i < num; i++) {
        let value = Math.floor(Math.random() * 6) + 1;
        values.push(value);
    }
    
    // Display results
    results.textContent = `${values}`;
}
```


### 12. Number Guessing
```js
let attempts=0;
let running=true;
let guess;
while(running){
    guess=window.prompt(`Enter a number between ${min} and ${max}`);
    guess=Number(guess);
    if(isNaN(guess)) alert("Enter a valid number");
    else if(guess<min && guess>max) alert("enter a valid number");
    else {
        if(guess<ans) {
            alert("Ans is greater than this");
            attempts++;
        }
        else if(guess>ans){
            alert("Ans is smaller than this");
            attempts++;
        }
        else {
            alert(`Congratulations. You took ${attempts} to find the ans ${ans}`);
            break;
        }
    }
}
```
