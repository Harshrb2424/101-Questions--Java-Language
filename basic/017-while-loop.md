## Problem Statement  
17. What is a `while` loop? Provide an example.

## Solution Code  
```java
public class WhileLoopExample {
    public static void main(String[] args) {
        int i = 1;

        // while loop to print numbers from 1 to 5
        while (i <= 5) {
            System.out.println("Iteration " + i);
            i++;
        }

        System.out.println("Loop ended.");
    }
}
```

## Explanation  
- **What is a `while` loop?**  
  A control flow statement that allows code to be executed **repeatedly** based on a given **boolean condition**.  
  - The loop continues **as long as the condition evaluates to `true`**.
  - It is also known as an **entry-controlled loop**, because the condition is checked **before** executing the loop body.

- **Syntax:**
  ```java
  while (condition) {
      // block of code to be executed
  }
  ```

- **Key Points:**
  - If the condition is initially `false`, the loop body will **not execute at all**.
  - Make sure to **update the loop variable** inside the loop, or you may end up with an **infinite loop**.

- **In This Example:**
  - We initialize `i = 1`.
  - Loop runs as long as `i <= 5`.
  - Inside the loop, we print the current value of `i` and then increment it by 1.

## Output  
```
Iteration 1
Iteration 2
Iteration 3
Iteration 4
Iteration 5
Loop ended.
```