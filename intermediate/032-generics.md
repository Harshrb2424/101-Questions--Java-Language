## Problem Statement  
32. What are generics? Provide an example.

## Solution Code  
```java
public class GenericsExample {
    public static void main(String[] args) {
        // Using the generic Box class with Integer type
        Box<Integer> integerBox = new Box<>();
        integerBox.setContents(100);
        System.out.println("Integer Box contains: " + integerBox.getContents());

        // Using the generic Box class with String type
        Box<String> stringBox = new Box<>();
        stringBox.setContents("Hello, Generics!");
        System.out.println("String Box contains: " + stringBox.getContents());

        // Compilation error if you try to add incorrect type
        // integerBox.setContents("This will cause a compile-time error"); // Uncommenting this line will cause error
    }
}

// Generic class
class Box<T> {
    private T contents;

    public void setContents(T contents) {
        this.contents = contents;
    }

    public T getContents() {
        return contents;
    }
}
```

## Explanation  

### ✅ What Are Generics in Java?
- **Generics** allow types (`classes` and `interfaces`) to be parameters when defining:
  - **Classes**
  - **Interfaces**
  - **Methods**

- This enables writing **type-safe** and **reusable code** without casting or risking `ClassCastException`.

> 💡 Generics were introduced in Java 5 to provide **compile-time type checking** and eliminate the need for explicit type casting.

---

### 📌 Key Benefits of Generics:

| Benefit | Description |
|--------|-------------|
| **Type Safety** | Ensures that you can only put the correct type into a collection or structure |
| **Code Reusability** | Write one class/method that works with any type |
| **Compile-time Checking** | Catches type mismatches at compile time instead of runtime |

---

### 🧠 How Generics Work

In the above example:
- We define a **generic class**: `Box<T>`
  - `T` is a **type parameter** — it acts as a placeholder for the actual type.
- When creating an object:
  - `Box<Integer>` means `T` becomes `Integer`
  - `Box<String>` means `T` becomes `String`

Each instance behaves like a box specific to its declared type.

---

### 🚫 Without Generics (Before Java 5)

You could store anything in a container but had to cast back manually:
```java
Box box = new Box();
box.setContents("Hello");
Integer value = (Integer) box.getContents(); // Runtime ClassCastException
```

With **generics**, such errors are caught at **compile time**, not runtime.

---

### 📁 Output

```
Integer Box contains: 100
String Box contains: Hello, Generics!
```

---

## Summary  
- **Generics** allow classes, interfaces, and methods to accept **type parameters**.
- They help write **flexible and reusable** code while maintaining **type safety**.
- Use them when designing collections, utility classes, or frameworks where data types vary but logic remains consistent.

> ⚠️ Generics do not support primitive types directly; use wrapper classes like `Integer`, `Double`, etc.