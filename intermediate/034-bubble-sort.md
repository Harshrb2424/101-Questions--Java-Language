## Problem Statement  
34. Write a program to sort an array using **Bubble Sort**.

## Solution Code  
```java
import java.util.Arrays;

public class BubbleSortExample {
    public static void main(String[] args) {
        int[] numbers = {5, 2, 9, 1, 3};

        System.out.println("Original array: " + Arrays.toString(numbers));

        bubbleSort(numbers);

        System.out.println("Sorted array: " + Arrays.toString(numbers));
    }

    // Bubble sort implementation
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;

        for (int i = 0; i < n - 1; i++) {
            swapped = false;

            // Last i elements are already sorted
            for (int j = 0; j < n - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap arr[j] and arr[j + 1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

            // If no two elements were swapped by inner loop, then break
            if (!swapped)
                break;
        }
    }
}
```

## Explanation  

### ✅ What is Bubble Sort?
- **Bubble Sort** is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.
- This process is repeated until the list is sorted.

> 🧠 The algorithm gets its name because smaller elements "bubble" to the top of the list gradually.

---

### 🧮 How It Works:
Let’s take the array: `{5, 2, 9, 1, 3}`

**Pass 1:**
- Compare `5` and `2` → swap → `{2, 5, 9, 1, 3}`
- Compare `5` and `9` → no swap
- Compare `9` and `1` → swap → `{2, 5, 1, 9, 3}`
- Compare `9` and `3` → swap → `{2, 5, 1, 3, 9}`

**Pass 2:**
- Continue comparing and swapping until no swaps are needed

**Optimization:**  
The `swapped` flag helps optimize the algorithm — if no swaps occur in an iteration, the array is already sorted.

---

### 🕒 Time Complexity:

| Case        | Time Complexity |
|-------------|------------------|
| Worst Case  | O(n²)            |
| Best Case   | O(n) (with optimization) |
| Average Case| O(n²)            |

Space Complexity: **O(1)** – In-place sorting

---

### 📌 Output  
```
Original array: [5, 2, 9, 1, 3]
Sorted array: [1, 2, 3, 5, 9]
```

---

## Summary  
- **Bubble Sort** is easy to understand and implement.
- Efficient only for small datasets or nearly sorted arrays.
- Uses nested loops and can be optimized with a `swapped` flag.
- A fundamental algorithm often used in teaching sorting techniques.

> 💡 For larger datasets, prefer more efficient algorithms like Quick Sort, Merge Sort, or built-in `Arrays.sort()`.