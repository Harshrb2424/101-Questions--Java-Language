## Problem Statement  
37. Write a program to find duplicates in an array.

## Solution Code  
```java
import java.util.HashSet;

public class FindDuplicatesInArray {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 2, 4, 5, 1, 6};

        System.out.println("Duplicate elements in the array:");

        findDuplicates(numbers);
    }

    // Method to find duplicate elements using HashSet
    public static void findDuplicates(int[] arr) {
        HashSet<Integer> seen = new HashSet<>();
        HashSet<Integer> duplicates = new HashSet<>();

        for (int num : arr) {
            if (!seen.add(num)) {
                duplicates.add(num); // If already exists, it's a duplicate
            }
        }

        // Print all unique duplicate values
        for (int dup : duplicates) {
            System.out.println(dup);
        }
    }
}
```

## Explanation  

### ✅ What This Program Does:
- It finds and prints **duplicate elements** from an integer array.
- Uses two `HashSet` collections:
  - One to keep track of elements we've already seen.
  - Another to store unique duplicate values.

---

### 🧠 How It Works:
1. Iterate through the input array.
2. For each number:
   - Try adding it to the `seen` set.
   - If it fails to add (because it already exists), it’s a duplicate.
   - Add that number to the `duplicates` set.
3. Finally, print all the duplicate numbers.

> 💡 `HashSet` ensures constant-time performance (`O(1)`) for insertions and lookups, making this approach efficient.

---

### 🕒 Time and Space Complexity:

| Metric | Value |
|--------|-------|
| Time Complexity | O(n) – Linear scan through the array |
| Space Complexity | O(n) – Extra space used by hash sets |

---

### 📌 Output  
For the given array `{1, 2, 3, 2, 4, 5, 1, 6}`:  
```
Duplicate elements in the array:
1
2
```

---

## Summary  
- This program efficiently identifies **unique duplicate elements** in an array using `HashSet`.
- It avoids nested loops and provides a clean solution with linear time complexity.
- Ideal for large arrays where performance matters.

> 💡 You can modify this logic to work with other data types like `String`, or custom objects, as long as they properly implement `hashCode()` and `equals()`.