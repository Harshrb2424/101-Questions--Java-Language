## Problem Statement  
18. Explain `break` and `continue` statements.

## Solution Code  
```java
public class BreakContinueExample {
    public static void main(String[] args) {

        // Example of 'break' statement
        System.out.println("Using break:");
        for (int i = 1; i <= 10; i++) {
            if (i == 6) {
                break; // Exit loop when i is 6
            }
            System.out.print(i + " ");
        }

        System.out.println("\nBreak loop ended.\n");

        // Example of 'continue' statement
        System.out.println("Using continue:");
        for (int j = 1; j <= 10; j++) {
            if (j % 2 == 0) {
                continue; // Skip even numbers
            }
            System.out.print(j + " ");
        }

        System.out.println("\nContinue loop ended.");
    }
}
```

## Explanation  
- ### `break` Statement:
  - Used to **terminate** a loop or switch statement.
  - Once encountered, the control immediately exits the loop or block.
  - Commonly used with conditional checks to terminate early.

  **In the example:**
  ```java
  if (i == 6) {
      break;
  }
  ```
  The loop stops when `i` reaches 6.

- ### `continue` Statement:
  - Used to **skip** the current iteration of a loop and move to the next one.
  - Control goes back to the loop condition instead of exiting entirely.

  **In the example:**
  ```java
  if (j % 2 == 0) {
      continue;
  }
  ```
  Even numbers are skipped from being printed.

- **Key Differences:**

| Feature     | `break`                        | `continue`                      |
|-------------|--------------------------------|----------------------------------|
| Purpose     | Exits the loop entirely        | Skips current iteration only     |
| Control Flow| Goes to the statement after loop| Goes back to the loop condition  |

## Output  
```
Using break:
1 2 3 4 5 
Break loop ended.

Using continue:
1 3 5 7 9 
Continue loop ended.
```