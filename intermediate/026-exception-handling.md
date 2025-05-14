## Problem Statement  
26. What is exception handling? Explain `try-catch` blocks.

## Solution Code  
```java
public class ExceptionHandlingExample {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println("Accessing element at index 5: " + numbers[5]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Exception caught: Array index is out of bounds!");
        }

        System.out.println("Program continues after exception handling.");
    }
}
```

## Explanation  

### ✅ What is Exception Handling?
- **Exception handling** is a mechanism in Java to handle runtime errors so that the normal flow of the program can continue.
- It helps prevent abrupt termination of the program and allows developers to gracefully recover from exceptional situations.

> Examples of exceptions:
> - `ArithmeticException` (e.g., division by zero)
> - `NullPointerException` (accessing methods on a null object)
> - `ArrayIndexOutOfBoundsException` (index out of range)
> - `NumberFormatException` (invalid parsing)

---

### 🔧 What are `try-catch` Blocks?

#### `try` block:
- Contains the code that might throw an exception.
- Must be followed by either a `catch` or a `finally` block (or both).

#### `catch` block:
- Handles the exception thrown in the `try` block.
- Multiple `catch` blocks can be used to handle different types of exceptions.

#### Syntax:
```java
try {
    // code that may throw an exception
} catch (ExceptionType1 e1) {
    // handle exception of type ExceptionType1
} catch (ExceptionType2 e2) {
    // handle exception of type ExceptionType2
}
```

---

### 📌 Key Points:
| Feature | Description |
|--------|-------------|
| `try` | Block where risky code is placed |
| `catch` | Catches and handles exceptions |
| Multiple Exceptions | Can use multiple `catch` blocks for different error types |
| `finally` | Optional block that always executes (used for cleanup code like closing files or connections) |

---

### 💡 Example Output
If you run the above program:
```
Exception caught: Array index is out of bounds!
Program continues after exception handling.
```

Without exception handling, the program would crash when accessing `numbers[5]`.

---

## Summary  
- **Exception handling** helps manage runtime errors effectively.
- Use `try-catch` blocks to detect and handle exceptions without crashing your program.
- Proper use of exception handling increases **robustness**, **maintainability**, and **readability** of your Java programs.

> ⚠️ Note: Always specify specific exceptions in `catch` blocks instead of using a generic `Exception` unless you want to catch all possible exceptions.