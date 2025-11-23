# 10e)  Types of Queue-Circular Queue in Python

This project demonstrates the implementation of a **Circular Queue** in Python. The queue accepts 3 user values, performs enqueue and dequeue operations, and displays the removed values.

---

##  Aim

To develop a Python program that implements a Circular Queue:
- Accepts 3 values from the user
- Removes the 3 values from the queue
- Displays the removed values

---

##  Algorithm

1. **Initialize** a circular queue of fixed size (e.g., 5).
2. **Define the following functions**:
   - `enqueue()`: Inserts an element into the queue.
   - `dequeue()`: Removes an element from the queue.
   - `display()`: Shows the queue contents.
3. Accept 3 values from the user using the `enqueue()` method.
4. Remove 3 values using the `dequeue()` method.
5. Print the removed values.

---

##  Program:
```
class MyCircularQueue():
    def __init__(self, k):
        self.k = k
        self.queue = [None] * k
        self.head = self.tail = -1

    def enqueue(self, data):
        if ((self.tail + 1) % self.k == self.head):
            print("The circular queue is full")
        elif (self.head == -1):
            self.head = 0
            self.tail = 0
            self.queue[self.tail] = data
        else:
            self.tail = (self.tail + 1) % self.k
            self.queue[self.tail] = data

    def dequeue(self):
        if (self.head == -1):
            print("The circular queue is empty")
        elif (self.head == self.tail):
            self.queue[self.head] = None
            self.head = -1
            self.tail = -1
        else:
            self.queue[self.head] = None
            self.head = (self.head + 1) % self.k

    def printCQueue(self):
        if self.head == -1:
            print("Queue is empty")
        else:
            i = self.head
            result = []
            while True:
                if self.queue[i] is not None:
                    result.append(str(self.queue[i]))
                if i == self.tail:
                    break
                i = (i + 1) % self.k
            print(" ".join(result))


# ----- Main Program -----
obj = MyCircularQueue(5)

for _ in range(5):
    obj.enqueue(int(input()))

# Remove 3 values
for _ in range(3):
    obj.dequeue()

# Display remaining values
obj.printCQueue()
```

### Output:
<img width="436" height="398" alt="image" src="https://github.com/user-attachments/assets/bd4dddb0-e81e-4f73-af1f-3adb5da01c06" />

## Result:
Program executed Successfully.
