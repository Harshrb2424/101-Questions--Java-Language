## Problem Statement  
13. Write a program to reverse a string.  

## Solution Code  
```java  
import java.util.Scanner;  

public class StringReverser {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
        System.out.print("Enter a string: ");  
        String input = scanner.nextLine();  
        String reversed = new StringBuilder(input).reverse().toString();  
        System.out.println("Reversed string: " + reversed);  
    }  
}  
```  

## Explanation  
- **Approach**: Uses `StringBuilder` for efficient string reversal.  
  - `StringBuilder(input)`: Wraps the input string.  
  - `.reverse()`: Reverses the characters in-place (O(n) time).  
  - `.toString()`: Converts the reversed `StringBuilder` back to a `String`.  
- **Alternative Manual Method**:  
  ```java  
  String reversed = "";  
  for (int i = input.length() - 1; i >= 0; i--) {  
      reversed += input.charAt(i);  
  }  
  ```  
  - Iterates backward through the input string and builds the reversed string.  
  - Less efficient due to repeated string concatenation.  
- **Edge Cases Handled**:  
  - Empty strings, single-character strings, and Unicode characters.  

## Output  
```  
Enter a string: Hello, World!  
Reversed string: !dlroW ,olleH  
```