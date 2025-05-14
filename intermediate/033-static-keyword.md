## Problem Statement  
33. Explain the `static` keyword with examples.

## Solution Code  
```java
public class StaticKeywordExample {

    // Static variable
    static String companyName = "Tech Corp";

    // Instance variable
    String employeeName;

    // Static method
    public static void displayCompanyInfo() {
        System.out.println("Company Name: " + companyName);
        // System.out.println("Employee Name: " + employeeName); // ❌ Compilation error - cannot access non-static from static
    }

    // Constructor
    public StaticKeywordExample(String name) {
        this.employeeName = name;
    }

    // Static block
    static {
        System.out.println("Static block initialized.");
    }

    public static void main(String[] args) {
        // Accessing static method and variable without object
        System.out.println("Accessing static variable directly: " + companyName);
        displayCompanyInfo();

        // Creating objects to show instance vs static behavior
        StaticKeywordExample emp1 = new StaticKeywordExample("Alice");
        StaticKeywordExample emp2 = new StaticKeywordExample("Bob");

        // Static variable shared across all instances
        companyName = "InnovateX";

        System.out.println("\nAfter updating company name:");
        emp1.displayCompanyInfo(); // Still uses updated static value
        emp2.displayCompanyInfo();
    }
}
```

## Explanation  

### ✅ What is the `static` Keyword in Java?

The `static` keyword is a **modifier** used for variables, methods, blocks, and nested classes. It belongs to the **class**, not to an **instance (object)** of the class.

> 💡 This means you can access `static` members **without creating an object** of the class.

---

### 📌 Features of `static` Members

| Feature | Description |
|--------|-------------|
| Belongs to class | Not tied to any specific object |
| Shared among all instances | Only one copy exists, no matter how many objects are created |
| Accessed using class name | E.g., `ClassName.staticMember` |
| Can be initialized before any object of the class is created | Through `static` block or declaration |

---

### 🔧 Types of `static` Elements

#### 1. **Static Variable (Class Variable)**  
- Shared by all objects.
- Useful for constants or values common to all instances.

```java
static String companyName;
```

#### 2. **Static Method (Class Method)**  
- Can only access other `static` variables/methods.
- Cannot refer to `this` or `super`.

```java
public static void displayCompanyInfo()
```

#### 3. **Static Block**  
- Used for initializing static data members.
- Executed **once**, when the class is loaded into memory.

```java
static {
    System.out.println("Static block initialized.");
}
```

---

### 🔄 Example Output

```
Static block initialized.
Accessing static variable directly: Tech Corp
Company Name: Tech Corp

After updating company name:
Company Name: InnovateX
Company Name: InnovateX
```

---

### 🚫 Important Restrictions:
- A `static` method **cannot access non-static members directly**.
- `this` and `super` **cannot be used** in a static context.

---

## Summary  
- Use `static` for variables and methods that should belong to the **class level**, not to individual objects.
- Use it for utility methods, constants, and logic that doesn’t depend on object state.
- Be cautious — misuse of `static` can lead to **tight coupling**, **difficulty in testing**, and **shared mutable state issues**.

> ⚠️ Static members are initialized in the order they appear in the code.