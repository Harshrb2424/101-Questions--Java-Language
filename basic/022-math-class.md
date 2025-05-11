## Problem Statement  
22. What is the `Math` class? Give an example of its use.

## Solution Code  
```java
public class MathClassExample {
    public static void main(String[] args) {

        // Example usage of Math class methods
        double num1 = 25.0;
        double num2 = -10.5;
        double a = 3.0, b = 4.0;

        System.out.println("Absolute value of " + num2 + ": " + Math.abs(num2));
        System.out.println("Square root of " + num1 + ": " + Math.sqrt(num1));
        System.out.println(num1 + " raised to the power of 2: " + Math.pow(num1, 2));
        System.out.println("Maximum of " + a + " and " + b + ": " + Math.max(a, b));
        System.out.println("Random number between 0 and 1: " + Math.random());
    }
}
```

## Explanation  

### ✅ What is the `Math` class?
- The `Math` class is part of the `java.lang` package.
- It provides **methods** for performing **basic numeric operations** such as:
  - Square roots (`sqrt`)
  - Exponentiation (`pow`)
  - Absolute value (`abs`)
  - Minimum/Maximum (`min`, `max`)
  - Random number generation (`random`)
  - Trigonometric functions (`sin`, `cos`, `tan`)
  - Logarithmic functions (`log`, `log10`), and more.

- All methods in the `Math` class are **static**, so you don’t need to create an instance to use them.

---

### 🔧 Commonly Used Methods in the `Math` Class:

| Method           | Description                         | Example                        |
|------------------|-------------------------------------|--------------------------------|
| `Math.abs(x)`    | Returns absolute value of `x`       | `Math.abs(-5)` → `5`          |
| `Math.sqrt(x)`   | Returns square root of `x`          | `Math.sqrt(16)` → `4.0`       |
| `Math.pow(x, y)` | Returns `x` raised to the power `y` | `Math.pow(2, 3)` → `8.0`      |
| `Math.max(x, y)` | Returns maximum of two values       | `Math.max(3, 7)` → `7.0`      |
| `Math.random()`  | Returns random value in [0.0, 1.0)  | —                              |

---

## Output  
```
Absolute value of -10.5: 10.5
Square root of 25.0: 5.0
25.0 raised to the power of 2: 625.0
Maximum of 3.0 and 4.0: 4.0
Random number between 0 and 1: 0.89231123456789 (value varies on each run)
```

## Summary  
- The `Math` class provides ready-to-use mathematical functions.
- Use it to simplify calculations without writing custom logic.
- All methods are accessed using the class name directly: `Math.methodName(...)`.