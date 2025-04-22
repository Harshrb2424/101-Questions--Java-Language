## Problem Statement  
10. Explain the `switch` statement with an example.  

## Solution Code  
```java  
public class DayChecker {  
    public static void main(String[] args) {  
        int day = 3;  
        switch (day) {  
            case 1:  
                System.out.println("Monday");  
                break;  
            case 2:  
                System.out.println("Tuesday");  
                break;  
            case 3:  
                System.out.println("Wednesday");  
                break;  
            default:  
                System.out.println("Invalid day");  
        }  
    }  
}  
```  

## Explanation  
- **`switch` Statement**:  
  - Evaluates a variable against multiple **constant values**.  
  - Executes the matching `case` block.  
  - **`break`**: Exits the switch block to prevent "fall-through".  
  - **`default`**: Optional; runs if no cases match.  
- **Example Logic**:  
  - `day = 3` matches `case 3`, printing "Wednesday".  
  - If `day` were 5, the `default` case would execute.  

## Output  
```  
Wednesday  
```