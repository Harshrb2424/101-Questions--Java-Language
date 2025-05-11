## Problem Statement  
24. Write a program to calculate factorial iteratively.

## Solution Code  
```java
import java.util.Scanner;

public class FactorialIterative {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number to calculate its factorial: ");
        int number = scanner.nextInt();

        if (number < 0) {
            System.out.println("Factorial is not defined for negative numbers.");
        } else {
            long factorial = 1;
            for (int i = 1; i <= number; i++) {
                factorial *= i;
            }
            System.out.println("Factorial of " + number + " is: " + factorial);
        }

        scanner.close();
    }
}
```

## Explanation  

### ✅ What is a Factorial?
The **factorial** of a non-negative integer `n`, denoted as `n!`, is the product of all positive integers less than or equal to `n`.

- Example:  
  `5! = 5 × 4 × 3 × 2 × 1 = 120`

### 🧠 How This Program Works:
1. Takes input from the user using `Scanner`.
2. Checks if the number is negative — if so, displays an error message.
3. Otherwise, uses a `for` loop to compute the factorial iteratively.
4. Uses a `long` to store the result to handle larger values (up to `20!` safely).

> ⚠️ Note: Factorials grow very fast. Even `20!` is `2432902008176640000`. Beyond that, use `BigInteger` for arbitrary precision.

---

## Output  
```
Enter a number to calculate its factorial: 5
Factorial of 5 is: 120
```

Another example:
```
Enter a number to calculate its factorial: 0
Factorial of 0 is: 1
```

---

## Summary  
- This program calculates the factorial using a simple iterative approach.
- Iteration is efficient and avoids stack overflow issues that can occur with recursion.
- Always validate input before performing mathematical operations.