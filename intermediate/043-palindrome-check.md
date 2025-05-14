## Problem Statement  
43. Write a program to check for palindromes.

## Solution Code  
```java
import java.util.Scanner;

public class PalindromeCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a string to check if it is a palindrome: ");
        String input = scanner.nextLine();

        if (isPalindrome(input)) {
            System.out.println("The input is a palindrome.");
        } else {
            System.out.println("The input is not a palindrome.");
        }

        scanner.close();
    }

    // Method to check if a string is a palindrome
    public static boolean isPalindrome(String str) {
        // Remove spaces and convert to lowercase for case-insensitive comparison
        String cleaned = str.replaceAll("\\s+", "").toLowerCase();

        int left = 0;
        int right = cleaned.length() - 1;

        while (left < right) {
            if (cleaned.charAt(left) != cleaned.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }

        return true;
    }
}
```

## Explanation  

### ✅ What is a Palindrome?
A **palindrome** is a word, phrase, number, or other sequence of characters that reads the same forward and backward (ignoring spaces, punctuation, and capitalization).

> Examples:
> - "racecar"
> - "madam"
> - "A man a plan a canal Panama"

---

### 🧠 How This Program Works

1. The user enters a string.
2. The `isPalindrome()` method:
   - **Cleans the string**: Removes whitespace and converts to lowercase.
   - Uses two pointers (`left` and `right`) to compare characters from both ends.
   - If any pair of characters doesn't match, it returns `false`.
   - If all pairs match, it returns `true`.

---

### 🕒 Time and Space Complexity

| Metric | Value |
|--------|-------|
| Time Complexity | O(n), where n is the length of the string |
| Space Complexity | O(n), due to the cleaned string |

---

### 📌 Output Examples

#### Example 1:
```
Enter a string to check if it is a palindrome: Racecar
The input is a palindrome.
```

#### Example 2:
```
Enter a string to check if it is a palindrome: Hello World
The input is not a palindrome.
```

#### Example 3:
```
Enter a string to check if it is a palindrome: A man a plan a canal Panama
The input is a palindrome.
```

---

## Summary  
- This program checks whether a given string is a **palindrome** by comparing characters from both ends.
- It handles **case insensitivity** and **ignores spaces**.
- Useful for validating inputs like passwords, symmetric text patterns, and data validation tasks.

> 💡 You can further enhance this program by removing non-alphanumeric characters for more robust palindrome checking.