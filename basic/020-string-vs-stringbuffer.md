## Problem Statement  
20. What is the `String` class? How is it different from `StringBuffer`?

## Solution Code  
```java
public class StringVsStringBuffer {
    public static void main(String[] args) {

        // Example with String (immutable)
        String str = "Hello";
        System.out.println("Original String: " + str);
        str += " World";  // Creates a new String object
        System.out.println("Updated String: " + str);

        // Example with StringBuffer (mutable)
        StringBuffer sb = new StringBuffer("Hello");
        System.out.println("\nOriginal StringBuffer: " + sb);
        sb.append(" World");  // Modifies the same object
        System.out.println("Updated StringBuffer: " + sb);
    }
}
```

## Explanation  

### ✅ What is the `String` class?
- The `String` class represents **immutable** sequences of characters.
- Once a `String` object is created, its value **cannot be changed**.
- Any operation that modifies a `String` (like concatenation or substring) results in the creation of a **new String object**.

### ✅ What is `StringBuffer`?
- `StringBuffer` is a **mutable** sequence of characters.
- It allows you to modify the content (append, insert, delete, replace, etc.) without creating a new object.
- It is **thread-safe**, meaning all its methods are `synchronized`.

---

### 🔁 Key Differences Between `String` and `StringBuffer`:

| Feature             | `String`                              | `StringBuffer`                           |
|---------------------|----------------------------------------|------------------------------------------|
| Mutability         | Immutable (can't change once created) | Mutable (can be modified)               |
| Performance        | Slower for modifications              | Faster for modifications                |
| Thread Safety      | Yes (but immutable)                   | Yes (`synchronized`)                    |
| Memory Usage       | Creates new objects on modification   | Modifies in-place                       |
| Use Case           | Fixed data, simple access             | Frequent modifications in single/multi-threaded environment |

---

## Output  
```
Original String: Hello
Updated String: Hello World

Original StringBuffer: Hello
Updated StringBuffer: Hello World
```

## Summary  
- Use **`String`** when the data won’t change.
- Use **`StringBuffer`** when you need **frequent modifications** and/or **thread safety**.