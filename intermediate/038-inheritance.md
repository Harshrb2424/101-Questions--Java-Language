## Problem Statement  
38. What is inheritance? Provide a code example.

## Solution Code  
```java
// Base class (Parent class)
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

// Derived class (Child class) - inherits from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Dog myDog = new Dog();

        myDog.eat();  // Inherited method from Animal
        myDog.bark(); // Own method
    }
}
```

## Explanation  

### ✅ What is Inheritance?
- **Inheritance** is one of the core concepts of **Object-Oriented Programming (OOP)**.
- It allows a class (**child/subclass**) to inherit properties and behaviors (i.e., methods and fields) from another class (**parent/superclass**).

> 🧠 This promotes **code reusability**, **method overriding**, and **hierarchical relationships** between classes.

---

### 🔧 How Inheritance Works:
- The `extends` keyword is used in Java for inheritance.
- In the example:
  - `Animal` is the **superclass (base class)**.
  - `Dog` is the **subclass (derived class)**.
  - `Dog` inherits all non-private members (methods and variables) from `Animal`.

---

### 📌 Key Terms

| Term | Description |
|------|-------------|
| Superclass | The class being inherited from |
| Subclass | The class that inherits from another class |
| `extends` | Java keyword used to create a subclass |
| Reusability | Subclass can reuse code from superclass |
| Method Overriding | Subclass can provide its own implementation of a method defined in the superclass |

---

### 🔄 Example Breakdown

- `Animal` class defines a general behavior: `eat()`.
- `Dog` class inherits `eat()` and adds a specific behavior: `bark()`.
- When you create an object of `Dog`, it can access both its own and inherited methods.

---

### 📁 Output  
```
This animal eats food.
The dog barks.
```

---

## Summary  
- **Inheritance** allows a class to inherit fields and methods from another class.
- Use `extends` to implement inheritance in Java.
- Promotes **code reuse**, **modularity**, and **logical hierarchies** in object-oriented design.

> 💡 Java supports single inheritance (a class can extend only one class), but multiple levels of inheritance are allowed (`A → B → C`).