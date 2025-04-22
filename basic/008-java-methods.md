
## Problem Statement  
8. What is a method in Java? Define a method to add two numbers.  

## Solution Code  
```java  
public class MathOperations {  
    // Method to add two numbers  
    public static int add(int a, int b) {  
        return a + b;  
    }  

    public static void main(String[] args) {  
        int result = add(5, 3);  
        System.out.println("5 + 3 = " + result);  
    }  
}  
```  

## Explanation  
- **Method Definition**:  
  - **Signature**: `public static int add(int a, int b)`  
    - `public`: Accessible from other classes.  
    - `static`: Belongs to the class (no object needed).  
    - `int`: Return type (result of addition).  
    - `a, b`: Parameters (input values).  
  - **Body**: Returns the sum of `a` and `b`.  
- **Usage**: Called in `main` with arguments `5` and `3`.  

## Output  
```  
5 + 3 = 8  
```