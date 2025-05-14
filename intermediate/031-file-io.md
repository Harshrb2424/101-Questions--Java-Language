## Problem Statement  
31. Write a program to read/write text to a file.

## Solution Code  
```java
import java.io.*;

public class FileReadWriteExample {
    public static void main(String[] args) {
        String fileName = "sample.txt";
        String contentToWrite = "Hello, this is some text written to a file using Java.";

        // Writing to a file
        try (FileWriter writer = new FileWriter(fileName)) {
            writer.write(contentToWrite);
            System.out.println("Successfully wrote to the file: " + fileName);
        } catch (IOException e) {
            System.out.println("An error occurred while writing to the file.");
            e.printStackTrace();
        }

        // Reading from the file
        try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {
            String line;
            System.out.println("\nReading content from the file:");
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("An error occurred while reading from the file.");
            e.printStackTrace();
        }
    }
}
```

## Explanation  

### ✅ What This Program Does:
- **Writes** a predefined string to a file named `sample.txt`.
- Then **reads back** the content from that file and prints it to the console.

---

### 🛠️ Key Classes Used:

| Class | Purpose |
|-------|---------|
| `FileWriter` | Writes character-based data to a file |
| `BufferedReader` | Reads text from a character-input stream efficiently |
| `FileReader` | Reads character-based data from a file |
| `try-with-resources` | Ensures automatic resource management (auto-close files) |

---

### 🧠 How It Works:
1. **Writing to the File**
   - A `FileWriter` object is created with the filename.
   - The `write()` method writes the string into the file.
   - The file is automatically closed after writing due to `try-with-resources`.

2. **Reading from the File**
   - A `FileReader` is wrapped inside a `BufferedReader` for efficient line-by-line reading.
   - The `readLine()` method reads each line until the end of the file (`null`).
   - Again, resources are automatically closed.

> 💡 Note: If the file does not exist when writing, it will be created automatically. When reading, if the file doesn’t exist or is empty, an appropriate message won't print or an exception may occur.

---

### 📁 Output

```
Successfully wrote to the file: sample.txt

Reading content from the file:
Hello, this is some text written to a file using Java.
```

After running the program, you'll find a file named `sample.txt` in the same directory containing the written text.

---

## Summary  
- Java provides simple yet powerful I/O classes like `FileWriter`, `FileReader`, and `BufferedReader` for basic file handling.
- Use `try-with-resources` for clean and safe resource management.
- Writing and reading files is essential for logging, configuration, and persistent data storage in many applications.