## Problem Statement  
35. What is method overloading? Give an example.

## Solution Code  
```java
public class MethodOverloadingExample {

    // Method with no parameters
    public void greet() {
        System.out.println("Hello!");
    }

    // Method with one String parameter
    public void greet(String name) {
        System.out.println("Hello, " + name + "!");
    }

    // Method with two parameters: String and int
    public void greet(String name, int age) {
        System.out.println("Hello, " + name + "! You are " + age + " years old.");
    }

    public static void main(String[] args) {
        MethodOverloadingExample example = new MethodOverloadingExample();

        example.greet();                     // Calls greet()
        example.greet("Alice");              // Calls greet(String)
        example.greet("Bob", 25);            // Calls greet(String, int)
    }
}
```

## Explanation  

### ✅ What is Method Overloading?
- **Method overloading** is a feature in Java that allows a class to have **more than one method with the same name**, as long as their **parameter lists are different**.
- It’s one of the ways Java supports **compile-time polymorphism**.

> 📌 Method overloading is **not based on return type** or access modifiers — only the number, type, or order of parameters matters.

---

### 🔧 Rules for Method Overloading:
| Rule | Description |
|------|-------------|
| Same method name | But... |
| Different parameters | Must differ in: <br> - Number of parameters <br> - Type of parameters <br> - Order of parameters |
| Return type not considered | Methods cannot be overloaded if they only differ by return type |

---

### 🔄 Example Breakdown

In this example:
```java
public void greet() { ... }                 // No parameters
public void greet(String name) { ... }      // One String parameter
public void greet(String name, int age) { ... } // Two parameters (String, int)
```

Each `greet` method behaves differently depending on what arguments you pass.

---

### 📌 Output  
```
Hello!
Hello, Alice!
Hello, Bob! You are 25 years old.
```

---

## Summary  
- **Method overloading** improves code readability and reusability.
- It allows methods to perform similar tasks with different inputs.
- Always ensure that the **parameter list differs** to enable proper method resolution at compile time.

> 💡 Use method overloading when methods perform logically the same operation but with different kinds of input.