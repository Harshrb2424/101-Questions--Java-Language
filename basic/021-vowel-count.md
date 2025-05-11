## Problem Statement  
21. Write a program to count vowels in a string.

## Solution Code  
```java
import java.util.Scanner;

public class VowelCount {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        int vowelCount = countVowels(input);
        System.out.println("Number of vowels in the string: " + vowelCount);

        scanner.close();
    }

    // Method to count vowels in a string
    public static int countVowels(String str) {
        int count = 0;
        String lowerStr = str.toLowerCase();  // Convert to lowercase for easy comparison

        for (int i = 0; i < lowerStr.length(); i++) {
            char ch = lowerStr.charAt(i);
            if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
                count++;
            }
        }

        return count;
    }
}
```

## Explanation  
- **What are vowels?**  
  The letters `a`, `e`, `i`, `o`, and `u` (both uppercase and lowercase) in the English alphabet.

- **Steps in the Program:**
  1. Read a string from the user using `Scanner`.
  2. Convert the input string to lowercase so we can compare each character with lowercase vowels only.
  3. Loop through each character of the string:
     - If the character is a vowel, increment the counter.
  4. Print the total number of vowels found.

- **Time Complexity:**  
  O(n), where n is the length of the input string.

## Output  
```
Enter a string: Hello World!
Number of vowels in the string: 3
```

Another example:
```
Enter a string: Java Programming
Number of vowels in the string: 5
```