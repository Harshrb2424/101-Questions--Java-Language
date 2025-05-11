## Problem Statement  
23. Explain the `default` keyword in a `switch` case.

## Solution Code  
```java
public class SwitchDefaultExample {
    public static void main(String[] args) {
        int day = 6;

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
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            default:
                System.out.println("Weekend or invalid day!");
                break;
        }
    }
}
```

## Explanation  

### ✅ What is the `default` keyword in a `switch` statement?
- The `default` block is **optional** in a `switch` statement.
- It gets executed **when none of the `case` values match** the expression provided to the `switch`.

### 🔧 How it works:
- Java evaluates the `switch` expression (`day` in this example).
- It then looks for a matching `case` label.
- If no match is found and a `default` block exists, that block runs.

> 💡 Tip: It’s good practice to include a `default` block to handle unexpected or invalid input.

---

### 📌 Key Points:
| Feature         | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| Optional         | You can skip `default`, but it's recommended for error handling             |
| Placement        | Can be placed anywhere in the `switch`, not necessarily at the end        |
| No Break Needed  | Like other cases, but using `break` avoids fall-through if desired          |

---

## Output  
For `int day = 6;`  
```
Weekend or invalid day!
```

Try changing `day` to any value from 1 to 5 to see corresponding weekdays.

---

## Summary  
- Use the `default` block in a `switch` to handle unmatched or unexpected cases.
- Improves code robustness by avoiding silent failures on invalid input.