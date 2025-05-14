## Problem Statement  
36. How does `HashMap` work internally?

## Solution Code  
```java
import java.util.HashMap;

public class HashMapExample {
    public static void main(String[] args) {
        // Creating a HashMap
        HashMap<String, Integer> employeeAges = new HashMap<>();

        // Putting key-value pairs into HashMap
        employeeAges.put("Alice", 30);
        employeeAges.put("Bob", 25);
        employeeAges.put("Charlie", 35);

        // Retrieving values
        System.out.println("Alice's age: " + employeeAges.get("Alice"));

        // Checking if key exists
        System.out.println("Contains key 'Bob'? " + employeeAges.containsKey("Bob"));

        // Removing an entry
        employeeAges.remove("Charlie");

        // Displaying final map
        System.out.println("Final HashMap: " + employeeAges);
    }
}
```

## Explanation  

### ✅ What is `HashMap`?
- `HashMap` is part of Java's **Collection Framework** (`java.util.HashMap`) and implements the `Map` interface.
- It stores data in **key-value pairs** and allows fast retrieval using keys.

---

### 🔍 Internal Working of `HashMap`

#### 1. **Data Structure: Array + LinkedList (or Balanced Tree in Java 8+)**
- Internally, `HashMap` uses an array of `Node<K,V>` objects called **buckets or bins**.
- Each bucket can hold a **linked list or a balanced tree (from Java 8)** to resolve hash collisions.

#### 2. **Hashing Mechanism**
- When you insert a key-value pair using `put(key, value)`:
  - The `hashCode()` method of the key object is called.
  - A hash function converts this hash code into an index within the internal array (bucket index).
  - If multiple keys have the same bucket index, they are stored as entries in a linked list (or tree for performance).

#### 3. **Collision Handling**
- **Collision** occurs when two different keys produce the same bucket index.
- Java handles this using **chaining** — storing multiple entries in the same bucket using a linked list.
- From **Java 8**, if a bucket grows beyond a threshold (TREEIFY_THRESHOLD = 8), it is converted into a **balanced red-black tree** for faster access.

#### 4. **Load Factor & Resizing**
- **Load factor** (default = 0.75f) determines how full the HashMap can be before resizing.
- When the number of elements exceeds `capacity * load factor`, the HashMap **resizes itself (doubles capacity)** and **rehashes all keys**.

---

### 🧠 Key Concepts

| Concept | Description |
|--------|-------------|
| `hashCode()` | Returns an integer that determines the bucket index |
| `equals()` | Compares keys to determine if they're the same |
| Hash Collision | When two different keys map to the same bucket |
| Bucket | An index in the internal array where entries are stored |
| Rehashing | Happens during resize; redistributes entries into new larger array |

---

### 📌 Output  
```
Alice's age: 30
Contains key 'Bob'? true
Final HashMap: {Alice=30, Bob=25}
```

---

## Summary  
- `HashMap` works internally by combining **hashing**, **array indexing**, and **linked list/tree structures**.
- It provides **O(1)** average time complexity for basic operations like `put()` and `get()`.
- Proper implementation of `hashCode()` and `equals()` is essential for custom objects used as keys.

> 💡 In Java 8+, `HashMap` uses **trees instead of lists** for buckets with many collisions to improve worst-case performance from O(n) to O(log n).