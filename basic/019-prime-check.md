## Problem Statement  
19. Write a program to check if a number is prime.

## Solution Code  
```java
import java.util.Scanner;

public class PrimeCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int number = scanner.nextInt();

        if (isPrime(number)) {
            System.out.println(number + " is a prime number.");
        } else {
            System.out.println(number + " is not a prime number.");
        }

        scanner.close();
    }

    // Method to check if a number is prime
    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false; // Found a factor, not prime
            }
        }
        return true; // No factors found, it's prime
    }
}
```

## Explanation  
- **What is a Prime Number?**  
  A number greater than 1 that has no positive divisors other than 1 and itself.

- **Steps in the Program:**  
  1. Read input from the user using `Scanner`.
  2. Handle edge cases:
     - Numbers less than or equal to 1 are not prime.
  3. Use a loop from 2 to √`num` to check divisibility:
     - If any number divides `num` evenly, it’s **not prime**.
     - If no divisors are found, it **is prime**.
  4. Print the result accordingly.

- **Efficiency Insight:**  
  Looping up to √`num` reduces unnecessary checks and improves performance significantly for large numbers.

## Output  
```
Enter a number: 29
29 is a prime number.
```

Another example:
```
Enter a number: 15
15 is not a prime number.
```