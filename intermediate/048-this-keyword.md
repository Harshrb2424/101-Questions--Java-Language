## Problem Statement  
48. Explain the `this` keyword in Java.

## Solution Code  
```java
public class ThisKeywordExample {
    private int id;
    private String name;

    // Constructor with parameters
    public ThisKeywordExample(int id, String name) {
        this.id = id;           // 'this' refers to current object's field
        this.name = name;
    }

    // Method to display values
    public void display() {
        System.out.println("ID: " + this.id);
        System.out.println("Name: " + this.name);
    }

    // Method to show using 'this' to call another constructor
    public ThisKeywordExample() {
        this(0, "Unknown");  // Calls parameterized constructor
        System.out.println("Default constructor called");
    }

    public static void main(String[] args) {
        ThisKeywordExample obj1 = new ThisKeywordExample(1, "Alice");
        obj1.display();

        ThisKeywordExample obj2 = new ThisKeywordExample();  // Invokes default constructor
    }
}
```

## Explanation  

### ✅ What is the `this` Keyword?

The `this` keyword in Java is a **reference variable** that refers to the **current object** — the object on which the method is being called.

It is used to:
- Distinguish between **instance variables and local variables** when they have the same name.
- Call **another constructor** of the same class (constructor chaining).
- Pass the current object as an argument in method calls or constructor calls.

---

### 🛠️ Uses of `this` Keyword

#### 1. **Referring to Instance Variables**
When a method or constructor has a parameter with the same name as an instance variable, `this.variableName` helps distinguish them.

```java
public ThisKeywordExample(int id, String name) {
    this.id = id;
    this.name = name;
}
```

#### 2. **Calling Another Constructor**
You can use `this()` to invoke another constructor from within a constructor — known as **constructor chaining**.

```java
public ThisKeywordExample() {
    this(0, "Unknown");
}
```

> ⚠️ If used, it must be the **first statement** in the constructor.

#### 3. **Returning the Current Object**
You can return `this` from a method to return the current object for method chaining.

```java
public MyClass setValue(int value) {
    this.value = value;
    return this;
}
```

#### 4. **Passing `this` as an Argument**
Useful when passing the current object to another method or constructor.

```java
someMethod(this);
```

---

### 📌 Key Points About `this`

| Feature | Description |
|--------|-------------|
| Can't be assigned | You cannot assign a value to `this` (`this = null;` is invalid) |
| Cannot be used in static context | Static methods do not belong to any object, so `this` is unavailable |
| Must be first in constructor call | When calling one constructor from another using `this()`, it must be the first line |

---

### 📁 Output  
```
ID: 1
Name: Alice
Default constructor called
```

---

## Summary  
- The `this` keyword refers to the **current instance** of the class.
- It’s useful for resolving naming conflicts, constructor chaining, returning or passing the current object.
- Understanding `this` improves code clarity and supports clean object-oriented design.

> 💡 Use `this` consistently to make your code more readable and maintainable, especially in constructors and setters.