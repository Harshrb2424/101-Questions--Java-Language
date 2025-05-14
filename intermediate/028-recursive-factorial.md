## Problem Statement  
28. Write a recursive program to calculate the factorial of a number.

## Solution Code  
```java
import java.util.Scanner;

public class RecursiveFactorial {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number to calculate its factorial: ");
        int number = scanner.nextInt();

        if (number < 0) {
            System.out.println("Factorial is not defined for negative numbers.");
        } else {
            long result = factorial(number);
            System.out.println("Factorial of " + number + " is: " + result);
        }

        scanner.close();
    }

    // Recursive method to calculate factorial
    public static long factorial(int n) {
        if (n == 0 || n == 1) {
            return 1; // Base case
        } else {
            return n * factorial(n - 1); // Recursive call
        }
    }
}
```

## Explanation  

### ✅ What is Recursion?
Recursion is a programming technique where a method calls itself to solve smaller instances of the same problem.

### ✅ What is the Factorial of a Number?
The **factorial** of a non-negative integer `n`, denoted as `n!`, is the product of all positive integers less than or equal to `n`.

- Example:  
  `5! = 5 × 4 × 3 × 2 × 1 = 120`

### 🧠 How This Program Works:
1. The user inputs a number.
2. The program checks for invalid input (negative number).
3. If valid, it calls the `factorial()` method recursively.
4. The base case (`n == 0` or `n == 1`) stops recursion.
5. Each recursive call reduces the problem size by computing `n * factorial(n - 1)`.

> ⚠️ Note: Be cautious with large input values — deep recursion can cause **stack overflow errors**. For large factorials, consider using iteration or `BigInteger` with iterative approach.

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
- This program uses **recursion** to compute the factorial of a number.
- It demonstrates the use of a **base case** and a **recursive case**.
- Recursion is elegant but should be used carefully due to stack limitations.