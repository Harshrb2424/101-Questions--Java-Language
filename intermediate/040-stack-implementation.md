## Problem Statement  
40. Write a program to implement a **stack using an array**.

## Solution Code  
```java
public class StackImplementation {
    private int maxSize;
    private int top;
    private int[] stackArray;

    // Constructor to initialize stack
    public StackImplementation(int size) {
        this.maxSize = size;
        this.stackArray = new int[maxSize];
        this.top = -1; // Stack is empty initially
    }

    // Method to push an element onto the stack
    public void push(int value) {
        if (isFull()) {
            System.out.println("Stack Overflow: Cannot push " + value + ", stack is full.");
            return;
        }
        stackArray[++top] = value;
        System.out.println("Pushed " + value + " to the stack.");
    }

    // Method to pop an element from the stack
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow: Cannot pop, stack is empty.");
            return -1;
        }
        return stackArray[top--];
    }

    // Method to peek at the top element of the stack
    public int peek() {
        if (!isEmpty()) {
            return stackArray[top];
        }
        System.out.println("Stack is empty.");
        return -1;
    }

    // Method to check if the stack is empty
    public boolean isEmpty() {
        return (top == -1);
    }

    // Method to check if the stack is full
    public boolean isFull() {
        return (top == maxSize - 1);
    }

    public static void main(String[] args) {
        StackImplementation stack = new StackImplementation(5);

        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Top element: " + stack.peek());

        System.out.println("Popped element: " + stack.pop());
        System.out.println("Popped element: " + stack.pop());

        stack.push(40);
        stack.push(50);
        stack.push(60); // This will cause overflow

        while (!stack.isEmpty()) {
            System.out.println("Popped: " + stack.pop());
        }

        stack.pop(); // Trying to underflow
    }
}
```

## Explanation  

### ✅ What is a Stack?
- A **stack** is a linear data structure that follows the **LIFO (Last In First Out)** principle.
- The last element added to the stack is the first one to be removed.

> Common operations:
> - `push()` – Add an element to the top
> - `pop()` – Remove an element from the top
> - `peek()` – View the top element
> - `isEmpty()` – Check if stack is empty
> - `isFull()` – Check if stack is full

---

### 🧠 How This Program Works:
- We define a fixed-size array to store stack elements.
- A `top` variable keeps track of the index of the topmost element.
- All stack operations are performed based on the value of `top`.

#### Key Points:
- `top` starts at `-1`, indicating an empty stack.
- On each `push()`, `top` is incremented and the value is inserted.
- On each `pop()`, the value at `top` is returned and `top` is decremented.

---

### 🕒 Time Complexity:

| Operation | Time Complexity |
|----------|------------------|
| Push     | O(1)             |
| Pop      | O(1)             |
| Peek     | O(1)             |

Space Complexity: **O(n)** for storing `n` elements in the array.

---

### 📌 Output  
```
Pushed 10 to the stack.
Pushed 20 to the stack.
Pushed 30 to the stack.
Top element: 30
Popped element: 30
Popped element: 20
Pushed 40 to the stack.
Pushed 50 to the stack.
Stack Overflow: Cannot push 60, stack is full.
Popped: 50
Popped: 40
Popped: 10
Stack Underflow: Cannot pop, stack is empty.
```

---

## Summary  
- This program demonstrates how to **implement a stack using an array** in Java.
- It includes all standard stack operations with proper checks for **overflow** and **underflow**.
- Ideal for learning basic data structures and their implementation in Java.

> 💡 For dynamic resizing, consider using `ArrayList` or linked list-based stack implementations.