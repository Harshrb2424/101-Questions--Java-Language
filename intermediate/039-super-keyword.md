## Problem Statement  
39. Explain the `super` keyword.

## Solution Code  
```java
class Animal {
    String name;

    Animal(String name) {
        this.name = name;
    }

    void display() {
        System.out.println("Animal name: " + name);
    }
}

class Dog extends Animal {
    String breed;

    Dog(String name, String breed) {
        super(name);  // Calling superclass constructor
        this.breed = breed;
    }

    void display() {
        super.display();  // Calling superclass method
        System.out.println("Breed: " + breed);
    }
}

public class SuperKeywordExample {
    public static void main(String[] args) {
        Dog dog = new Dog("Buddy", "Golden Retriever");
        dog.display();
    }
}
```

## Explanation  

### ✅ What is the `super` Keyword?
- The `super` keyword in Java is a reference variable used to refer to the **immediate parent class object**.
- It allows access to:
  - Parent class **constructors**
  - Parent class **methods**
  - Parent class **variables (fields)**

> 💡 Used inside a subclass to call or refer to its superclass members.

---

### 🛠️ Uses of `super` Keyword

#### 1. **Calling Superclass Constructor**
```java
super(); 
```
- Must be the **first statement** in the subclass constructor.
- Used to initialize parent class fields when creating a child class object.

#### 2. **Calling Superclass Method**
```java
super.methodName();
```
- Useful when subclass overrides a method and still wants to use the parent version.

#### 3. **Accessing Superclass Field**
```java
super.variableName;
```
- Used when both superclass and subclass have variables with the same name.

---

### 🔄 Example Breakdown

In the above code:
- `Animal` is the **superclass**, and `Dog` is the **subclass**.
- In the `Dog` constructor:
  ```java
  super(name);
  ```
  This calls the parameterized constructor of the `Animal` class.

- In the `display()` method of `Dog`:
  ```java
  super.display();
  ```
  This calls the `display()` method from the `Animal` class before printing the breed.

---

### 📁 Output  
```
Animal name: Buddy
Breed: Golden Retriever
```

---

## Summary  
- The `super` keyword is essential for accessing superclass members in a subclass.
- Use it to:
  - Call superclass constructors
  - Access overridden methods
  - Refer to hidden fields
- Always place `super()` as the first line in a constructor if you're calling a superclass constructor.

> ⚠️ Avoid confusion between `this` (current class) and `super` (parent class).