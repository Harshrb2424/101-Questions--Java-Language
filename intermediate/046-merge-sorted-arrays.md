## Problem Statement  
46. Write a program to merge two sorted arrays.

## Solution Code  
```java
import java.util.Arrays;

public class MergeSortedArrays {
    public static void main(String[] args) {
        int[] arr1 = {1, 3, 5, 7};
        int[] arr2 = {2, 4, 6, 8};

        System.out.println("Array 1: " + Arrays.toString(arr1));
        System.out.println("Array 2: " + Arrays.toString(arr2));

        int[] merged = mergeSortedArrays(arr1, arr2);

        System.out.println("Merged array: " + Arrays.toString(merged));
    }

    // Method to merge two sorted arrays
    public static int[] mergeSortedArrays(int[] arr1, int[] arr2) {
        int n1 = arr1.length;
        int n2 = arr2.length;
        int[] result = new int[n1 + n2];

        int i = 0, j = 0, k = 0;

        // Traverse both arrays and insert smaller element into result
        while (i < n1 && j < n2) {
            if (arr1[i] < arr2[j]) {
                result[k++] = arr1[i++];
            } else {
                result[k++] = arr2[j++];
            }
        }

        // Add remaining elements of arr1, if any
        while (i < n1) {
            result[k++] = arr1[i++];
        }

        // Add remaining elements of arr2, if any
        while (j < n2) {
            result[k++] = arr2[j++];
        }

        return result;
    }
}
```

## Explanation  

### ✅ What This Program Does:
- Merges **two sorted arrays** (`arr1` and `arr2`) into a **single sorted array**.
- Uses a **two-pointer technique** for efficient merging in linear time.

---

### 🧠 How It Works:

1. Initialize three pointers:
   - `i` for `arr1`
   - `j` for `arr2`
   - `k` for the `result` array

2. Compare elements from both arrays:
   - Insert the **smaller element** into the result array.
   - Move the corresponding pointer forward.

3. After one array is exhausted:
   - Copy remaining elements from the other array into the result.

---

### 🕒 Time and Space Complexity

| Metric | Value |
|--------|-------|
| Time Complexity | O(n + m), where `n` and `m` are lengths of input arrays |
| Space Complexity | O(n + m), for storing the merged array |

> ⏱️ This is optimal for merging two already-sorted arrays.

---

### 📌 Output  
```
Array 1: [1, 3, 5, 7]
Array 2: [2, 4, 6, 8]
Merged array: [1, 2, 3, 4, 5, 6, 7, 8]
```

---

## Summary  
- This program efficiently merges two **sorted integer arrays** into one sorted array.
- Uses a **greedy approach** with two pointers to ensure linear time complexity.
- Useful in divide-and-conquer algorithms like **merge sort** and for combining sorted datasets.

> 💡 This logic can be extended to merge more than two sorted arrays or used in external sorting applications.