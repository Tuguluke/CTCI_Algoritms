# Chapter examples 

Stack and Queue :

Java
```java
import java.util.EmptyStackException;

public class MyStack<T> {

    private static class StackNode<T> {
        private T data;
        private StackNode<T> next;

        public StackNode(T data) {
            this.data = data;
        }
    }

    private StackNode<T> top;

    public T pop() {
        if (top == null) throw new EmptyStackException();
        T item = top.data;
        top = top.next;
        return item;
    }

    public void push(T item) {
        StackNode<T> t = new StackNode<>(item);
        t.next = top;
        top = t;
    }

    public T peek() {
        if (top == null) throw new EmptyStackException();
        return top.data;
    }

    public boolean isEmpty() {
        return top == null;
    }
}

// testing
public class Main {
    public static void main(String[] args) {
        MyStack<Integer> stack = new MyStack<>();

        // Push elements onto the stack
        stack.push(1);
        stack.push(2);
        stack.push(3);

        // Pop elements from the stack
        System.out.println(stack.pop());  // Output: 3
        System.out.println(stack.pop());  // Output: 2

        // Check if the stack is empty
        System.out.println(stack.isEmpty());  // Output: false

        // Peek at the top element of the stack
        System.out.println(stack.peek());  // Output: 1

        // Pop the remaining element from the stack
        System.out.println(stack.pop());  // Output: 1

        // Check if the stack is empty
        System.out.println(stack.isEmpty());  // Output: true
    }
}

```

Python

```python
class MyStack:
    class StackNode:
        def __init__(self, data):
            self.data = data
            self.next = None

    def __init__(self):
        self.top = None

    def pop(self):
        if self.top is None:
            raise Exception("Stack is empty")
        item = self.top.data
        self.top = self.top.next
        return item

    def push(self, item):
        t = self.StackNode(item)
        t.next = self.top
        self.top = t

    def peek(self):
        if self.top is None:
            raise Exception("Stack is empty")
        return self.top.data

    def is_empty(self):
        return self.top is None


# Test the MyStack class
stack = MyStack()

# Push elements onto the stack
stack.push(1)
stack.push(2)
stack.push(3)

# Pop elements from the stack
print(stack.pop())  # Output: 3
print(stack.pop())  # Output: 2

# Check if the stack is empty
print(stack.is_empty())  # Output: False

# Peek at the top element of the stack
print(stack.peek())  # Output: 1

# Pop the remaining element from the stack
print(stack.pop())  # Output: 1

# Check if the stack is empty
print(stack.is_empty())  # Output: True
```
