## Problem Statement  
42. Explain the `transient` keyword.

## Solution Code  
```java
import java.io.*;

class User implements Serializable {
    private static final long serialVersionUID = 1L;

    String username;
    transient String password; // This field will not be serialized

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }

    @Override
    public String toString() {
        return "User{username='" + username + "', password='" + password + "'}";
    }
}

public class TransientKeywordExample {
    public static void main(String[] args) {
        String filename = "user.ser";

        // Creating and serializing an object
        try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream(filename))) {
            User user = new User("admin", "secret");
            out.writeObject(user);
            System.out.println("Object serialized: " + user);
        } catch (IOException e) {
            e.printStackTrace();
        }

        // Deserializing the object
        try (ObjectInputStream in = new ObjectInputStream(new FileInputStream(filename))) {
            User deserializedUser = (User) in.readObject();
            System.out.println("Object deserialized: " + deserializedUser);
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

## Explanation  

### ✅ What is the `transient` Keyword?
- The `transient` keyword is used in Java to **indicate that a field should not be part of the serialization process**.
- When an object is serialized (converted into a byte stream for storage or transmission), all its non-transient fields are saved.
- Fields marked as `transient` are **skipped during serialization**.

> 🧠 The `transient` keyword applies only to **instance variables**, not to methods or classes.

---

### 🔐 Why Use `transient`?

Useful when:
- You want to exclude sensitive data like passwords, API keys, etc., from being serialized.
- Some fields cannot or should not be serialized (e.g., file handles, threads, database connections).

---

### 🔄 Example Breakdown

In the example:
- The `User` class has two fields:
  - `username` – normal serializable field.
  - `password` – marked as `transient`, so it won't be saved when the object is serialized.

#### Output:
```
Object serialized: User{username='admin', password='secret'}
Object deserialized: User{username='admin', password='null'}
```

As you can see:
- The `password` field becomes `null` after deserialization because it was marked `transient`.

---

### 📌 Key Points About `transient`

| Feature | Description |
|--------|-------------|
| Applies to | Instance variables only |
| Purpose | Prevent field from being serialized |
| Default Value | `transient` fields are set to their default values (e.g., `null` for objects, `0` for int) after deserialization |
| Used with | `Serializable` interface |
| Not Applicable To | Static fields (they are never serialized anyway) |

---

### 📁 Output  
```
Object serialized: User{username='admin', password='secret'}
Object deserialized: User{username='admin', password='null'}
```

---

## Summary  
- The `transient` keyword prevents a field from being included during **object serialization**.
- Useful for **security-sensitive** or **non-serializable** fields.
- After deserialization, `transient` fields are initialized to their default values.
- It’s a key tool in managing what data gets persisted or transmitted across networks in Java applications.