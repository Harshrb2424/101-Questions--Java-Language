## Problem Statement  
47. What is the `Comparable` interface? Provide an example.

## Solution Code  
```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// A class that implements Comparable to define natural ordering
class Student implements Comparable<Student> {
    private String name;
    private int rollNumber;

    public Student(String name, int rollNumber) {
        this.name = name;
        this.rollNumber = rollNumber;
    }

    public String getName() {
        return name;
    }

    public int getRollNumber() {
        return rollNumber;
    }

    // Overriding compareTo to define natural ordering by roll number
    @Override
    public int compareTo(Student other) {
        return Integer.compare(this.rollNumber, other.rollNumber);
    }

    @Override
    public String toString() {
        return "Student{name='" + name + "', rollNumber=" + rollNumber + "}";
    }
}

public class ComparableExample {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("Alice", 102));
        students.add(new Student("Bob", 101));
        students.add(new Student("Charlie", 103));

        System.out.println("Before sorting:");
        for (Student student : students) {
            System.out.println(student);
        }

        // Sorting using Collections.sort(), which uses Comparable
        Collections.sort(students);

        System.out.println("\nAfter sorting by roll number:");
        for (Student student : students) {
            System.out.println(student);
        }
    }
}
```

## Explanation  

### ✅ What is the `Comparable` Interface?
- The `Comparable` interface is part of the `java.lang` package.
- It defines a **natural ordering** for objects of a class.
- It contains a single method:  
  ```java
  int compareTo(T o)
  ```
  - Returns:
    - Negative if the current object is less than the argument.
    - Zero if they are equal.
    - Positive if the current object is greater than the argument.

> 📌 Classes that implement `Comparable` can be sorted using `Collections.sort()` or `Arrays.sort()` without needing a custom comparator.

---

### 🔧 Why Use `Comparable`?

- To enable **default sorting behavior** for custom objects.
- Ensures consistency when sorting collections of that type.
- Useful when there’s a **single, logical way** to sort instances of a class.

---

### 🔄 Example Breakdown

In the code:
- The `Student` class implements `Comparable<Student>`.
- Overrides `compareTo()` to compare students based on their `rollNumber`.
- In `main()`, a list of students is created and sorted using `Collections.sort()`.

---

### 📌 Output  
```
Before sorting:
Student{name='Alice', rollNumber=102}
Student{name='Bob', rollNumber=101}
Student{name='Charlie', rollNumber=103}

After sorting by roll number:
Student{name='Bob', rollNumber=101}
Student{name='Alice', rollNumber=102}
Student{name='Charlie', rollNumber=103}
```

---

### 🧠 Key Points

| Feature | Description |
|--------|-------------|
| Package | `java.lang.Comparable` |
| Method | `int compareTo(T o)` |
| Purpose | Defines natural ordering for objects |
| Usage | Used by `Collections.sort()` and `Arrays.sort()` |
| Single Order Only | Can only define one default sort order |

---

### 💡 Comparison with `Comparator`
| Feature | `Comparable` | `Comparator` |
|--------|---------------|--------------|
| Defined in | `java.lang` | `java.util` |
| Method | `compareTo()` | `compare()` |
| Used for | Default sorting | Custom sorting |
| Number of Orders | One | Multiple |

---

## Summary  
- The `Comparable` interface allows Java classes to define a **natural ordering** for their objects.
- Implement `compareTo()` to specify how two instances should be ordered.
- Enables use of built-in sorting methods like `Collections.sort()` and `Arrays.sort()`.
- Ideal when you have a **single, standard way** to sort your custom objects.

> ⚠️ Always ensure `compareTo()` is consistent with `equals()` unless there's a good reason not to.