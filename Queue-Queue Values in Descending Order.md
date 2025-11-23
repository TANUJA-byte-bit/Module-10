# Module 10
# 10a) Queue- To sort the 5 float values in the Queue in descending order 

This Python program to sort the 5 float values in the Queue in descending order 

##  Aim
To write a python program to sort the 5 float values in the Queue in descending order 

##  Algorithm
1.Create an empty queue.

2.Take five float inputs from the user and insert each into the queue.

3.Find the total number of elements in the queue and store it in n.

4.Start sorting:

    Remove the first element and store it in x.

    Compare x with every other element one by one.

    Each time, remove the next element y from the queue.

    If x is smaller, put y back into the queue.

    If y is smaller, put x back and update x = y.

5.After finishing the inner comparison loop, put the smallest value (x) back into the queue.

6.Repeat the sorting steps for all elements in the queue.

7.When sorting is done, print each element by showing the front value and removing it.

8.Continue printing until the queue becomes empty.

9.End

##  Program: 
```
import queue  
q = queue.Queue() 
for i in range(5):
    q.put(float(input()))  

n =  q.qsize()  
for i in range(n):  
    x = q.get()  
    for j in range(n-1):  
        y = q.get()  
        if x < y :  
            q.put(y)  
        else:  
            q.put(x)  
            x = y     
    q.put(x)  
while (q.empty() == False):   
    print(q.queue[0], end = " ")    
    q.get()
```
### Output:
<img width="758" height="412" alt="image" src="https://github.com/user-attachments/assets/9165fb20-9bc6-4afc-95c5-1aba5a66e27e" />

## Result:
Program executed Successfully.
