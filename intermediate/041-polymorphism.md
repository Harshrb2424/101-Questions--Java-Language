## Problem Statement  
41. What is polymorphism? Differentiate between compile-time and runtime polymorphism.

## Solution Code  
```java
class Animal {
    // Method to be overridden
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat meows");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        // Compile-time polymorphism (method overloading - same class)
        Calculator calc = new Calculator();
        System.out.println("Add 2 integers: " + calc.add(5, 10));
        System.out.println("Add 3 integers: " + calc.add(5, 10, 15));
        System.out.println("Add 2 doubles: " + calc.add(2.5, 3.5));

        // Runtime polymorphism (method overriding - inheritance)
        Animal myAnimal = new Animal();  // Animal reference and object
        Animal myDog = new Dog();        // Animal reference but Dog object
        Animal myCat = new Cat();        // Animal reference but Cat object

        System.out.println();

        myAnimal.makeSound(); // Calls Animal's method
        myDog.makeSound();     // Calls Dog's overridden method
        myCat.makeSound();     // Calls Cat's overridden method
    }
}

// Supporting class for compile-time polymorphism
class Calculator {
    // Method with 2 int parameters
    int add(int a, int b) {
        return a + b;
    }

    // Overloaded method with 3 int parameters
    int add(int a, int b, int c) {
        return a + b + c;
    }

    // Overloaded method with 2 double parameters
    double add(double a, double b) {
        return a + b;
    }
}
```

## Explanation  

### ✅ What is Polymorphism?
- **Polymorphism** is one of the core principles of Object-Oriented Programming (OOP).
- It means **"many forms"**, allowing objects to be treated as objects of their parent class rather than their actual class.
- In Java, polymorphism allows a single action to be performed in different ways.

> There are two types of polymorphism in Java:
> 1. **Compile-Time Polymorphism (Static Binding)**  
> 2. **Runtime Polymorphism (Dynamic Binding)**

---

### 🔧 Compile-Time Polymorphism  
Also known as **static polymorphism**, it is achieved through **method overloading**.

#### Characteristics:
| Feature | Description |
|--------|-------------|
| Method Resolution | Done at **compile time** |
| Based on | Number, type, or order of arguments |
| Also Called | Static method dispatch |
| Example | Multiple `add()` methods with different parameters |

#### Example from Code:
```java
calc.add(5, 10);       // Calls add(int, int)
calc.add(5, 10, 15);   // Calls add(int, int, int)
calc.add(2.5, 3.5);    // Calls add(double, double)
```

---

### 🔄 Runtime Polymorphism  
Also known as **dynamic polymorphism**, it is achieved through **method overriding**.

#### Characteristics:
| Feature | Description |
|--------|-------------|
| Method Resolution | Done at **runtime** |
| Based on | Object type (not reference type) |
| Also Called | Dynamic method dispatch |
| Requires | Inheritance and method overriding |

#### Example from Code:
```java
Animal myDog = new Dog();
myDog.makeSound(); // Output: Dog barks
```
Even though the reference is of type `Animal`, the **object type (`Dog`)** determines which method is executed.

---

### 📌 Key Differences Between Compile-Time and Runtime Polymorphism

| Feature | Compile-Time Polymorphism | Runtime Polymorphism |
|--------|----------------------------|-----------------------|
| Type | Method Overloading | Method Overriding |
| Binding | Static (at compile time) | Dynamic (at runtime) |
| Based On | Method signature (number/type/order of parameters) | Object being referred |
| Use Case | Same class with multiple versions of the same method | Parent-child class relationship using inheritance |
| Performance | Faster (resolved at compile time) | Slightly slower (resolved at runtime) |
| Flexibility | Less flexible | More flexible and powerful |

---

### 📁 Output  
```
Add 2 integers: 15
Add 3 integers: 30
Add 2 doubles: 6.0

Animal makes a sound
Dog barks
Cat meows
```

---

## Summary  
- **Polymorphism** allows one interface to represent many implementations.
- **Compile-time polymorphism** uses method overloading and is resolved at compile time.
- **Runtime polymorphism** uses method overriding and is resolved at runtime based on the actual object.
- Together, they enable writing **flexible**, **reusable**, and **extensible** code.

> 💡 Always override methods when you want subclass-specific behavior while keeping a common interface in the superclass.