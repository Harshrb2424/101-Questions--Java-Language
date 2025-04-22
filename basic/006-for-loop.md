
## Problem Statement  
6. How does a `for` loop work? Provide a code snippet  

## Solution Code  
```java  
public class ForLoopExample {  
    public static void main(String[] args) {  
        for (int i = 1; i <= 5; i++) {  
            System.out.println("Iteration: " + i);  
        }  
    }  
}  
```  

## Explanation  
- **Syntax**:  
  ```java  
  for (initialization; condition; update) {  
      // code to repeat  
  }  
  ```  
- **Execution Flow**:  
  1. **Initialization**: Runs once at the start (`int i = 1`).  
  2. **Condition Check**: If `true`, execute the loop body; if `false`, exit.  
  3. **Update**: Runs after each iteration (`i++`).  
- **Example Logic**: Prints numbers 1 to 5 by incrementing `i` until `i <= 5` becomes `false`.  

## Output  
```  
Iteration: 1  
Iteration: 2  
Iteration: 3  
Iteration: 4  
Iteration: 5  
```