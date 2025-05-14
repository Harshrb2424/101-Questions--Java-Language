## Problem Statement  
30. Explain the `finally` block in exception handling.

## Solution Code  
```java
public class FinallyBlockExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // This will throw an ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Exception caught: Cannot divide by zero.");
        } finally {
            System.out.println("This is the finally block. Always executed.");
        }
    }
}
```

## Explanation  

### ✅ What is the `finally` Block?
- The `finally` block is a **special block used in exception handling**, always associated with a `try-catch` block.
- It is **used to execute important cleanup code** like closing files, database connections, or network resources — regardless of whether an exception occurs or is handled.

> 💡 The `finally` block is **always executed**, whether:
> - An exception is thrown and caught,
> - An exception is thrown but not caught,
> - Or no exception occurs at all.

---

### 🔄 Syntax Overview

```java
try {
    // Code that may throw an exception
} catch (ExceptionType e) {
    // Handle exception
} finally {
    // Always executed
}
```

---

### 🧠 Example Scenarios

#### 1. **No Exception**
```java
try {
    int result = 10 / 2;
    System.out.println("Result: " + result); // Output: 5
} catch (ArithmeticException e) {
    System.out.println("Exception occurred");
} finally {
    System.out.println("Finally block executed.");
}
```
**Output:**
```
Result: 5
Finally block executed.
```

#### 2. **Exception Caught**
```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Caught division by zero.");
} finally {
    System.out.println("Finally block executed.");
}
```
**Output:**
```
Caught division by zero.
Finally block executed.
```

#### 3. **Exception Not Caught**
```java
try {
    String str = null;
    System.out.println(str.length()); // Throws NullPointerException
} finally {
    System.out.println("Finally block executed.");
}
```
**Output:**
```
Finally block executed.
Exception in thread "main" java.lang.NullPointerException
```

---

### 📌 Key Points About `finally`:
| Feature | Description |
|--------|-------------|
| Always Executed | Regardless of exception occurrence or catching |
| Cleanup Purpose | Used for releasing resources (files, DB connections, etc.) |
| Can Be Skipped? | Only if JVM exits early (`System.exit()`), application crashes, or infinite loop in `try/catch` |

---

## Output *(From Given Code)*  
```
Exception caught: Cannot divide by zero.
This is the finally block. Always executed.
```

---

## Summary  
- The `finally` block ensures that critical code (like resource cleanup) runs **regardless of exceptions**.
- It follows `try` and optional `catch` blocks.
- Prefer using it when working with I/O operations, databases, or external services to avoid memory leaks or resource wastage.