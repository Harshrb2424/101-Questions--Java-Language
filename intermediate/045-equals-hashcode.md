## Problem Statement  
45. Explain the `equals()` and `hashCode()` methods.

## Solution Code  
```java
import java.util.Objects;

class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;

        Person person = (Person) obj;
        return age == person.age && Objects.equals(name, person.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + "}";
    }
}

public class EqualsHashCodeExample {
    public static void main(String[] args) {
        Person p1 = new Person("Alice", 30);
        Person p2 = new Person("Alice", 30);
        Person p3 = new Person("Bob", 25);

        System.out.println("p1.equals(p2): " + p1.equals(p2)); // true
        System.out.println("p1.equals(p3): " + p1.equals(p3)); // false

        System.out.println("p1.hashCode(): " + p1.hashCode());
        System.out.println("p2.hashCode(): " + p2.hashCode());
        System.out.println("p3.hashCode(): " + p3.hashCode());
    }
}
```

## Explanation  

### ✅ What is `equals()`?

- The `equals()` method is defined in the `Object` class.
- It is used to **compare the equality of two objects** based on their **content**, not reference.

#### Default Behavior:
```java
public boolean equals(Object obj) {
    return (this == obj);
}
```
This compares object references only.

> 🔁 Override `equals()` when you want to define **logical equality** for your custom class.

---

### ✅ What is `hashCode()`?

- The `hashCode()` method returns an integer value that represents the object.
- It is used by hash-based collections like `HashMap`, `HashSet`, and `Hashtable` to store and retrieve objects efficiently.

#### Default Behavior:
- Returns a unique integer based on the object’s memory address.

> 🔁 Override `hashCode()` whenever you override `equals()` to maintain the general contract:
> - If two objects are equal, they must have the same hash code.

---

### 🔄 Contract Between `equals()` and `hashCode()`

| Rule | Description |
|------|-------------|
| 1 | If `a.equals(b)` is `true`, then `a.hashCode() == b.hashCode()` must also be `true`. |
| 2 | If two objects have the same hash code, they may or may not be equal. |
| 3 | Always override both `equals()` and `hashCode()` together if you need to change how equality works for your class. |

---

### 📌 Why Are They Important?

- Used in **collections** like `Set` and `Map` to determine uniqueness and bucket placement.
- Essential for proper functioning of data structures that rely on hashing.
- Ensures consistency between logical equality and hash-based behavior.

---

### 🧠 Example Output

```
p1.equals(p2): true
p1.equals(p3): false
p1.hashCode(): 96384
p2.hashCode(): 96384
p3.hashCode(): 96385
```

As expected:
- `p1` and `p2` are logically equal → same hash code.
- `p3` is different → different hash code.

---

### 💡 Utility: `Objects.equals()` and `Objects.hash()`

Java provides utility methods from the `java.util.Objects` class:
- `Objects.equals(Object a, Object b)` – null-safe equality check.
- `Objects.hash(Object... values)` – convenient way to generate hash codes.

---

## Summary  
- `equals()` determines whether two objects are logically equal.
- `hashCode()` returns an integer used by hash-based collections.
- Always **override both** if you override one — maintaining their contract is crucial.
- These methods are essential for working with Java collections and ensuring correct object comparison and retrieval.

> ⚠️ Failing to override `hashCode()` after overriding `equals()` can lead to inconsistent behavior in hash-based collections.