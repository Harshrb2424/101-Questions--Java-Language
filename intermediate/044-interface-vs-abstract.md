## Problem Statement  
44. What is an interface? How is it different from an abstract class?

## Solution Code  
```java
// Interface example
interface Animal {
    void makeSound(); // Abstract method (no body)
}

// Abstract class example
abstract class Vehicle {
    // Concrete method
    void startEngine() {
        System.out.println("Engine started.");
    }

    // Abstract method
    abstract void move();
}

// Implementing the interface
class Dog implements Animal {
    public void makeSound() {
        System.out.println("Bark!");
    }
}

// Extending the abstract class
class Car extends Vehicle {
    void move() {
        System.out.println("Car is moving.");
    }
}

public class InterfaceVsAbstractClassExample {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // From interface

        Car car = new Car();
        car.startEngine(); // From abstract class
        car.move(); // Implemented in subclass
    }
}
```

## Explanation  

### ✅ What is an Interface?
- An **interface** in Java is a reference type, similar to a class, that can contain only:
  - **Abstract methods** (before Java 8)
  - **Default and static methods** (from Java 8+)
  - **Private methods** (from Java 9+)
- It supports **multiple inheritance**, meaning a class can implement multiple interfaces.

> 📌 Interfaces define what a class must do, not how it does it.

---

### ✅ What is an Abstract Class?
- An **abstract class** is a class that may contain:
  - **Abstract methods** (without implementation)
  - **Concrete methods** (with implementation)
- Cannot be instantiated directly; must be extended by another class.
- Supports **single inheritance** only — a class can extend only one abstract class.

---

### 🔍 Key Differences Between Interface and Abstract Class

| Feature | Interface | Abstract Class |
|--------|-----------|----------------|
| **Method Implementation** | Only abstract methods before Java 8<br>Default & static methods allowed from Java 8 | Can have both abstract and concrete methods |
| **Multiple Inheritance** | Supported (a class can implement multiple interfaces) | Not supported (only one abstract class can be extended) |
| **Constructors** | No constructors | Yes, can have constructors |
| **Access Modifiers** | All methods are implicitly `public` | Methods can have any access modifier |
| **Variables** | Implicitly `public static final` (constants) | Can have non-final variables |
| **Usage** | Used to achieve full abstraction and support multiple inheritance | Used when you want common code with some abstraction |

---

### 🔄 When to Use Which?

#### Use an **Interface** when:
- You need multiple inheritance of type.
- You want to define a contract for unrelated classes.
- You're designing APIs or frameworks.

#### Use an **Abstract Class** when:
- You want to share code among closely related classes.
- You need access modifiers or constructors.
- You want to provide a base class with some default behavior.

---

### 📁 Output  
```
Bark!
Engine started.
Car is moving.
```

---

## Summary  
- **Interfaces** allow defining a contract without implementation details and support multiple inheritance.
- **Abstract classes** allow partial implementation and are used for sharing code among related classes.
- Choose based on design needs:
  - Prefer **interfaces** for abstraction and flexibility.
  - Prefer **abstract classes** for shared logic and single inheritance structure.

> 💡 From Java 8+, interfaces can have method implementations via `default` and `static` methods, blurring the line between interfaces and abstract classes.