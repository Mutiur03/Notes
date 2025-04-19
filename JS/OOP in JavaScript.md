### 1. **Creating Objects**

1. **Object Literals:**

```javascript
const person = {
    name: "Alice",
    age: 25,
    greet: function() {
        return `Hello, my name is ${this.name}.`;
    }
};
console.log(person.greet()); // Output: Hello, my name is Alice.
```

1. **Using a Constructor Function:**

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.greet = function() {
        return `Hello, my name is ${this.name}.`;
    };
}
const bob = new Person("Bob", 30);
console.log(bob.greet()); // Output: Hello, my name is Bob.
```

### 2. **Prototypes and Inheritance**

Prototypes allow JavaScript objects to inherit properties and methods from other objects.

```javascript
function Animal(name) {
    this.name = name;
}
Animal.prototype.speak = function() {
    return `${this.name} makes a noise.`;
};
const dog = new Animal("Dog");
console.log(dog.speak()); // Output: Dog makes a noise.
```

### 3. **ES6 Classes**

ES6 introduced class syntax to make OOP easier and more readable.

```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    greet() {
        return `Hello, my name is ${this.name}.`;
    }
}
const charlie = new Person("Charlie", 35);
console.log(charlie.greet()); // Output: Hello, my name is Charlie.
```

### 4. **Inheritance in Classes**

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
    speak() {
        return `${this.name} makes a noise.`;
    }
}
class Dog extends Animal {
    speak() {
        return `${this.name} barks.`;
    }
}
const myDog = new Dog("Rex");
console.log(myDog.speak()); // Output: Rex barks.
```

### 5. **Encapsulation and Getters/Setters**

Encapsulation hides implementation details using private variables (using `#` in ES6+).

```javascript
class User {
    #password;
    constructor(username, password) {
        this.username = username;
        this.#password = password;
    }
    getPassword() {
        return "Hidden";
    }
}
const user = new User("JohnDoe", "securePass");
console.log(user.getPassword()); // Output: Hidden
```

### 6. **Polymorphism**

Polymorphism allows a method to be overridden in derived classes.

```javascript
class Shape {
    area() {
        return "Area not defined";
    }
}
class Circle extends Shape {
    constructor(radius) {
        super();
        this.radius = radius;
    }
    area() {
        return Math.PI * this.radius ** 2;
    }
}
const myCircle = new Circle(5);
console.log(myCircle.area()); // Output: 78.53981633974483
```
