## Problem Statement  
27. Differentiate between `ArrayList` and `LinkedList`.

## Solution Code  
```java
import java.util.ArrayList;
import java.util.LinkedList;

public class ArrayListVsLinkedListExample {
    public static void main(String[] args) {
        // Using ArrayList
        ArrayList<String> arrayList = new ArrayList<>();
        arrayList.add("Apple");
        arrayList.add("Banana");
        arrayList.add("Cherry");

        System.out.println("ArrayList: " + arrayList);

        // Using LinkedList
        LinkedList<String> linkedList = new LinkedList<>();
        linkedList.add("Xerox");
        linkedList.add("Yamaha");
        linkedList.add("Zebra");

        System.out.println("LinkedList: " + linkedList);
    }
}
```

## Explanation  

### ✅ What is `ArrayList`?
- **`ArrayList`** is part of the Java Collections Framework.
- It implements the `List` interface and uses a **dynamic array** to store elements.
- Allows duplicate elements, maintains insertion order, and supports random access using indexes.

### ✅ What is `LinkedList`?
- **`LinkedList`** also implements the `List` interface.
- Internally uses a **doubly linked list** to store elements.
- Also allows duplicates and maintains insertion order but does not support fast random access.

---

### 🔄 Key Differences Between `ArrayList` and `LinkedList`

| Feature                | `ArrayList`                                     | `LinkedList`                                      |
|------------------------|--------------------------------------------------|---------------------------------------------------|
| **Underlying Structure** | Dynamic Array                                   | Doubly Linked List                                |
| **Access Time**         | Fast (`O(1)`) – by index                        | Slow (`O(n)`) – needs traversal                   |
| **Insertion/Deletion**  | Slower if elements need shifting (`O(n)`)       | Faster at middle or beginning (`O(1)` with reference) |
| **Memory Usage**        | Less overhead (only array)                      | More memory (stores references to next/prev nodes)|
| **Use Case**            | Frequent reading/access operations              | Frequent insertions/deletions                     |
| **Implements**          | `List` only                                     | `List` and `Deque` interfaces                     |

---

### 💡 When to Use Which?

- Use **`ArrayList`** when:
  - You need frequent access to elements by index.
  - Insertions and deletions are rare or occur at the end.

- Use **`LinkedList`** when:
  - You frequently insert or remove elements from the beginning/middle.
  - You need to use it as a queue or deque (e.g., stacks, queues).

---

## Output  
```
ArrayList: [Apple, Banana, Cherry]
LinkedList: [Xerox, Yamaha, Zebra]
```

---

## Summary  
- Both `ArrayList` and `LinkedList` implement the `List` interface but differ significantly in performance and internal structure.
- Choose based on usage pattern:
  - Prefer **`ArrayList`** for read-heavy tasks.
  - Prefer **`LinkedList`** for write-heavy tasks involving frequent insertions/deletions.