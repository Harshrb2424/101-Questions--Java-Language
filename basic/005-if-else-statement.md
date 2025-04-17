## Problem Statement  
5. Explain the `if-else` statement with an example  

## Solution Code  
```java  
public class IfElseExample {  
    public static void main(String[] args) {  
        int number = 10;  
        if (number > 0) {  
            System.out.println("The number is positive.");  
        } else {  
            System.out.println("The number is non-positive.");  
        }  
    }  
}  
```  

## Explanation  
- **Syntax**:  
  ```java  
  if (condition) {  
      // code block executed if condition is true  
  } else {  
      // code block executed if condition is false  
  }  
  ```  
- **Key Points**:  
  - Evaluates a boolean condition (`true`/`false`).  
  - `else` block is optional.  
  - Can chain multiple conditions using `else if`.  
- **Example Logic**: Checks if `number` is greater than 0 and prints the result.  

---
