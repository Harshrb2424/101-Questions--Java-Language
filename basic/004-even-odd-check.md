
## Problem Statement  
4. Write a program to check if a number is even or odd.  

## Solution Code  
```java  
import java.util.Scanner;  

public class EvenOddChecker {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
        System.out.print("Enter a number: ");  
        int number = scanner.nextInt();  
        if (number % 2 == 0) {  
            System.out.println(number + " is even.");  
        } else {  
            System.out.println(number + " is odd.");  
        }  
    }  
}  
```  

## Explanation  
- **Input Handling**: Uses `Scanner` to read user input.  
- **Modulus Operator (`%`)**: Checks the remainder when divided by 2.  
  - If remainder is 0 → even.  
  - Else → odd.  
- **Edge Cases**: Works for zero, negative numbers, and positive integers.  

## Output  
```  
Enter a number: 7  
7 is odd.  
```