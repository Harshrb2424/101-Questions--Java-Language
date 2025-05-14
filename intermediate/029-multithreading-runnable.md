## Problem Statement  
29. What is multithreading? Create a thread using `Runnable`.

## Solution Code  
```java
public class MultithreadingUsingRunnable implements Runnable {
    @Override
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(Thread.currentThread().getName() + " - Count: " + i);
            try {
                Thread.sleep(500); // Pause for 500 milliseconds
            } catch (InterruptedException e) {
                System.out.println(Thread.currentThread().getName() + " interrupted.");
            }
        }
    }

    public static void main(String[] args) {
        // Creating threads using the Runnable interface
        Thread thread1 = new Thread(new MultithreadingUsingRunnable(), "Thread-1");
        Thread thread2 = new Thread(new MultithreadingUsingRunnable(), "Thread-2");

        // Starting the threads
        thread1.start();
        thread2.start();
    }
}
```

## Explanation  

### ✅ What is Multithreading?
- **Multithreading** is a Java feature that allows concurrent (simultaneous) execution of two or more parts of a program to maximize CPU utilization.
- Each part of such a program is called a **thread**, and all threads exist within a single process, sharing its resources.

> 🧠 A thread is a **lightweight process**.

---

### ✅ How to Create a Thread Using `Runnable` Interface

#### Steps:
1. **Implement the `Runnable` interface**: It has a single method `run()` which contains the code executed by the thread.
2. **Pass an instance of the `Runnable` to the `Thread` constructor**.
3. **Call `start()` on the `Thread` object**: This starts a new thread and executes the `run()` method.

---

### 🔄 Difference Between Extending `Thread` and Implementing `Runnable`
| Feature                      | Extend `Thread`                        | Implement `Runnable`                     |
|------------------------------|----------------------------------------|-------------------------------------------|
| Multiple Inheritance         | Not possible (Java doesn't allow)      | Possible (recommended approach)           |
| Code Reusability             | Less reusable                          | More reusable                             |
| Recommended                  | ❌ Not recommended                      | ✅ Yes, preferred                         |

---

### 📌 Key Concepts:
| Method              | Purpose |
|---------------------|---------|
| `run()`             | Contains the code that the thread will execute |
| `start()`           | Starts a new thread and calls `run()` internally |
| `Thread.sleep()`    | Pauses the current thread for specified time (in milliseconds) |
| `Thread.currentThread().getName()` | Gets the name of the currently executing thread |

---

## Output *(Sample)*  
Since threads are concurrent, the output may vary with each run:
```
Thread-1 - Count: 1
Thread-2 - Count: 1
Thread-1 - Count: 2
Thread-2 - Count: 2
Thread-1 - Count: 3
Thread-2 - Count: 3
...
```

The interleaving depends on how the JVM schedules the threads.

---

## Summary  
- **Multithreading** enables parallel execution of tasks.
- You can create a thread by implementing the `Runnable` interface and passing it to a `Thread` object.
- This approach is **flexible and preferred** over extending the `Thread` class.
- Use `start()` to begin execution and `run()` contains the logic executed by the thread.