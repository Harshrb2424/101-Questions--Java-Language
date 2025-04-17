## Problem Statement  
3. What is the difference between `int` and `Integer`?  

## Solution Code  
```java  
// Example using int  
int primitive = 42;  

// Example using Integer  
Integer wrapper = Integer.valueOf(42);  
```  

## Explanation  
- **`int`**: A primitive data type that stores numerical values directly.  
- **`Integer`**: A wrapper class that encapsulates an `int` value as an object.  
- Key differences:  
  - `Integer` can be `null`; `int` cannot.  
  - `Integer` is used in collections (e.g., `ArrayList<Integer>`).  
  - `int` is more memory-efficient for simple numerical operations.  
  - Autoboxing/unboxing allows automatic conversion between `int` and `Integer`.  

---
