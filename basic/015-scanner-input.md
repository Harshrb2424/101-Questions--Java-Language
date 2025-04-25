## Problem Statement  
15. How do you read input from the console using `Scanner`?  

## Solution Code  
```java  
import java.util.Scanner;  

public class ConsoleInputExample {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  

        System.out.print("Enter your name: ");  
        String name = scanner.nextLine();  

        System.out.print("Enter your age: ");  
        int age = scanner.nextInt();  

        System.out.println("Hello, " + name + "! You are " + age + " years old.");  

        scanner.close();  
    }  
}  
```  

## Explanation  
- **Steps to Read Input**:  
  1. **Import `Scanner`**: `import java.util.Scanner;`  
  2. **Create a `Scanner` Object**:  
     ```java  
     Scanner scanner = new Scanner(System.in);  
     ```  
     - `System.in` represents the standard input stream (keyboard).  
  3. **Read Input**:  
     - **`nextLine()`**: Reads a full line of text (e.g., a `String`).  
     - **`nextInt()`**: Reads an integer.  
     - Other methods: `nextDouble()`, `nextBoolean()`, etc.  
  4. **Close the Scanner**:  
     ```java  
     scanner.close();  
     ```  
     - Good practice to free resources (optional for small programs).  

- **Key Notes**:  
  - `Scanner` throws exceptions for invalid input (e.g., entering text for `nextInt()`).  
  - Use `hasNextInt()`/`hasNextLine()` to validate input types.  

## Output  
```  
Enter your name: Alice  
Enter your age: 30  
Hello, Alice! You are 30 years old.  
```