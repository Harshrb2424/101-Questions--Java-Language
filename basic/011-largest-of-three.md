## Problem Statement  
11. Write a program to find the largest of three numbers.  

## Solution Code  
```java  
import java.util.Scanner;  

public class LargestNumberFinder {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
        System.out.print("Enter first number: ");  
        int a = scanner.nextInt();  
        System.out.print("Enter second number: ");  
        int b = scanner.nextInt();  
        System.out.print("Enter third number: ");  
        int c = scanner.nextInt();  

        int max = a;  
        if (b > max) {  
            max = b;  
        }  
        if (c > max) {  
            max = c;  
        }  

        System.out.println("The largest number is: " + max);  
    }  
}  
```  

## Explanation  
- **Logic**:  
  1. Initialize `max` with the first number (`a`).  
  2. Compare `max` with the second number (`b`). If `b` is larger, update `max`.  
  3. Compare `max` with the third number (`c`). If `c` is larger, update `max`.  
- **Advantages**:  
  - Simple and readable.  
  - Works for **any combination** of values (including duplicates and negatives).  
- **Edge Cases**:  
  - All numbers equal: Returns the first occurrence.  
  - Two numbers equal and largest: Correctly identifies the duplicate.  

## Output  
```  
Enter first number: 12  
Enter second number: 7  
Enter third number: 15  
The largest number is: 15  
```