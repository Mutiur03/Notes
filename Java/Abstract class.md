
This class can't be initiated but can use on other classes.
Here we can initialize two types of function
1. Abstract
2. Concrete
In abstract we have to implement that function in child class but in the case of concrete implementation in not necessary.
```java
// Abstract class
abstract class Animal {
    abstract void makeSound(); // Abstract method
    void eat() { // Concrete method
        System.out.println("This animal eats food.");
    }
}
// Subclass that extends the abstract class
class Dog extends Animal {
    // Providing implementation for the abstract method
    @Override
    void makeSound() {
        System.out.println("Woof Woof");
    }
}
public class Main {
    public static void main(String[] args) {
        // Animal a = new Animal(); // Error: Cannot instantiate the abstract class
        Dog dog = new Dog(); // Create an object of the subclass
        dog.makeSound(); // Output: Woof Woof
        dog.eat();       // Output: This animal eats food.
    }
}
```