## Problem Statement  
16. Write a program to print Fibonacci series up to 10 terms.

## Solution Code  
```java
public class FibonacciSeries {
    public static void main(String[] args) {
        int n = 10, first = 0, second = 1;

        System.out.println("Fibonacci Series up to " + n + " terms:");

        for (int i = 1; i <= n; i++) {
            System.out.print(first + " ");

            int next = first + second;
            first = second;
            second = next;
        }
    }
}
```

## Explanation  
- **What is Fibonacci Series?**  
  A sequence where each number is the sum of the two preceding ones, starting from 0 and 1.  
  Example: `0 1 1 2 3 5 8 13 21 34`

- **Steps in the Program**:  
  1. Initialize the number of terms to print: `n = 10`.  
  2. Declare variables `first` and `second` to hold the current and next numbers in the series.  
  3. Use a `for` loop to iterate `n` times and generate the series:
     - Print the current value (`first`).  
     - Compute the next value by adding `first` and `second`.  
     - Update `first` and `second` for the next iteration.  

- **Efficiency**: This approach uses constant space O(1) and runs in linear time O(n).

## Output  
```
Fibonacci Series up to 10 terms:
0 1 1 2 3 5 8 13 21 34 
```