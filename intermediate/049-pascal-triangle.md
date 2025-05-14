Sure! Here's the content in your requested format:

---

## Problem Statement  
49. Write a program to print the **Pascal Triangle**.

## Solution Code  
```java
import java.util.Scanner;

public class PascalTriangle {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of rows for Pascal Triangle: ");
        int rows = scanner.nextInt();

        printPascalTriangle(rows);

        scanner.close();
    }

    // Method to print Pascal Triangle
    public static void printPascalTriangle(int n) {
        for (int i = 0; i < n; i++) {
            // Print spaces for triangle alignment
            for (int j = 0; j < n - i - 1; j++) {
                System.out.print(" ");
            }

            // Calculate and print values for each position in current row
            long value = 1;
            for (int j = 0; j <= i; j++) {
                System.out.print(value + " ");
                value = value * (i - j) / (j + 1);
            }

            System.out.println();
        }
    }
}
```

## Explanation  

### ✅ What is Pascal Triangle?
- **Pascal’s Triangle** is a triangular array of numbers where each number is the sum of the two numbers directly above it.
- The first and last value of each row is always `1`.
- It contains binomial coefficients which are used in combinatorics and algebra.

> Example for 5 rows:
```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

---

### 🧠 How This Program Works

1. The user inputs the number of rows.
2. For each row:
   - Spaces are printed to center-align the triangle.
   - Values are calculated using a formula based on combinations:
     ```
     C(n, k+1) = C(n, k) * (n - k) / (k + 1)
     ```
   - This avoids recomputing factorials every time and improves efficiency.

---

### 🕒 Time and Space Complexity

| Metric | Value |
|--------|-------|
| Time Complexity | O(n²) – Nested loop for rows and elements |
| Space Complexity | O(1) – No extra space used except for variables |

---

### 📌 Output Example

#### Input:
```
Enter the number of rows for Pascal Triangle: 5
```

#### Output:
```
    1 
   1 1 
  1 2 1 
 1 3 3 1 
1 4 6 4 1 
```

---

## Summary  
- This program prints **Pascal’s Triangle** up to a given number of rows.
- Efficiently calculates binomial coefficients using a multiplicative formula.
- Includes formatting to align the triangle neatly.

> 💡 Pascal Triangle is not only visually appealing but also has applications in probability, algebra, and algorithm design.

> Tip: You can enhance this by storing previous rows if you want to use dynamic programming for large triangles.