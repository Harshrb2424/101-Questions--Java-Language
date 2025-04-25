## Problem Statement  
12. What is type casting? Differentiate implicit vs explicit.  

## Solution Code  
```java  
// Implicit Casting Example  
int intValue = 42;  
double doubleValue = intValue; // Automatic widening conversion  

// Explicit Casting Example  
double anotherDouble = 3.14159;  
int anotherInt = (int) anotherDouble; // Manual narrowing conversion  
```  

## Explanation  
- **Type Casting**:  
  Converting a value from one data type to another.  

- **Implicit Casting (Widening)**:  
  - Automatically performed by Java.  
  - Converts a **smaller** type to a **larger** type (e.g., `int` → `double`).  
  - No data loss (e.g., `42` becomes `42.0`).  

- **Explicit Casting (Narrowing)**:  
  - Requires manual syntax `(target_type)`.  
  - Converts a **larger** type to a **smaller** type (e.g., `double` → `int`).  
  - Risk of data loss (e.g., `3.14159` becomes `3`).  

- **Key Differences**:  
  | **Aspect**          | **Implicit**                | **Explicit**                |  
  |----------------------|-----------------------------|-----------------------------|  
  | **Direction**        | Smaller → Larger            | Larger → Smaller            |  
  | **Syntax**           | Automatic                   | Requires `(type)`           |  
  | **Data Loss**        | None                        | Possible truncation/overflow|  
  | **Example**          | `int → double`              | `double → int`              |  

## Output  
```  
// After implicit casting:  
doubleValue = 42.0  

// After explicit casting:  
anotherInt = 3  
```