## Problem Statement  
50. How do you handle multiple exceptions in Java?

## Solution Code  
```java
public class MultipleExceptionHandling {
    public static void main(String[] args) {
        try {
            // Example 1: ArrayIndexOutOfBoundsException
            int[] numbers = {1, 2, 3};
            System.out.println("Accessing element at index 5: " + numbers[5]);

            // Example 2: ArithmeticException
            int result = 10 / 0;
            System.out.println("Result: " + result);

        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("Caught a general exception: " + e.getMessage());
        } finally {
            System.out.println("This block is always executed.");
        }
    }
}
```

## Explanation  

### ✅ What is Multiple Exception Handling?
- In Java, **multiple exceptions** can occur in a single block of code.
- You can handle them by using **multiple `catch` blocks** with specific exception types.

> This allows for **fine-grained error handling**, where different types of errors are handled differently.

---

### 🔄 How to Handle Multiple Exceptions

Use multiple `catch` blocks after a `try` block, ordered from **most specific to least specific**:

#### Syntax:
```java
try {
    // risky code
} catch (SpecificException1 e) {
    // handle exception type 1
} catch (SpecificException2 e) {
    // handle exception type 2
} catch (Exception e) {
    // handle any remaining exceptions (general case)
}
```

> ⚠️ Always place more specific exceptions first — otherwise, a general catch block may **swallow** specific ones and cause a compile-time error.

---

### 🧠 Example Breakdown

In this example:

- First, an `ArrayIndexOutOfBoundsException` is thrown when accessing `numbers[5]`.
- If that line is commented out or not executed, an `ArithmeticException` occurs due to division by zero.
- Each exception is caught by its respective `catch` block.

---

### 📌 Key Points

| Feature | Description |
|--------|-------------|
| Specificity | Catch specific exceptions before general ones |
| `finally` block | Always executes regardless of whether an exception occurred |
| `Exception` superclass | Can be used as a fallback to catch all other exceptions |
| Readability | Helps distinguish between different failure scenarios |

---

### 📁 Output *(Based on current code)*  
```
Caught ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 3
This block is always executed.
```

If you remove the array access and run only the division by zero:
```
Caught ArithmeticException: / by zero
This block is always executed.
```

---

## Summary  
- Use **multiple `catch` blocks** to handle different types of exceptions separately.
- Always order exception handlers from **most specific to most general**.
- Combine with `finally` to perform cleanup operations like closing files or network resources.

> 💡 Avoid catching `Throwable` or `Error` unless you have a very good reason — these are usually unrecoverable system-level issues.