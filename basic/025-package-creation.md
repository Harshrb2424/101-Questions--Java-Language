## Problem Statement  
25. What is a package in Java? How do you create one?

## Solution Code  

### Step 1: Define a class inside a package

```java
// File: com/example/myapp/HelloWorld.java
package com.example.myapp;

public class HelloWorld {
    public void greet() {
        System.out.println("Hello from package com.example.myapp!");
    }
}
```

### Step 2: Use the package in another class

```java
// File: Main.java
import com.example.myapp.HelloWorld;

public class Main {
    public static void main(String[] args) {
        HelloWorld hw = new HelloWorld();
        hw.greet();
    }
}
```

## Explanation  

### ✅ What is a Package in Java?
- A **package** is a mechanism for organizing Java classes into **modules or namespaces**.
- It helps avoid naming conflicts, control access, and make code more maintainable.

> 📁 Think of packages like folders in a file system — just as you organize files in directories, you organize classes in packages.

---

### 🛠️ How to Create a Package:
1. **Declare the package** using the `package` keyword at the top of the Java source file (before any class definition).
2. The directory structure should match the package name.
   - Example:  
     For package `com.example.myapp`, the folder structure should be:  
     ```
     com/
       example/
         myapp/
           HelloWorld.java
     ```

3. **Compile with proper directory structure**:
   ```bash
   javac -d . HelloWorld.java
   ```
   This command compiles the file and places the `.class` file under appropriate directories based on the package name.

4. **Run the program**:
   ```bash
   java com.example.myapp.HelloWorld
   ```

---

### 🔍 Using Classes from Other Packages:
To use a class from another package, you can:
- Use the full qualified class name:
  ```java
  com.example.myapp.HelloWorld hw = new com.example.myapp.HelloWorld();
  ```
- Or import it:
  ```java
  import com.example.myapp.HelloWorld;
  ```

---

### 📦 Types of Packages:
| Type              | Description |
|-------------------|-------------|
| Built-in Packages | E.g., `java.lang`, `java.util`, `java.io` |
| User-defined Packages | Created by developers to organize their own classes |

---

## Output  
If you run the `Main` class after compiling properly:
```
Hello from package com.example.myapp!
```

---

## Summary  
- **Packages** help organize Java classes and avoid naming conflicts.
- To create a package, use the `package` keyword at the top of the file and follow the corresponding folder structure.
- Use `import` to access classes from other packages.
- Packages enhance **modularity**, **accessibility control**, and **maintainability** in large Java applications.