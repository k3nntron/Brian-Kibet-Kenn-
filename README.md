# Brian-Kibet-Kenn
"""
DATA STRUCTURES AND ALGORITHMS ASSIGNMENT

Definition:
A Data Structure is a group of data elements that provides
an efficient way of storing and organizing data so that it
can be used efficiently.
"""
# 1. BASIC TERMINOLOGY

print("===== BASIC TERMINOLOGY =====")

data = "Student Name and ID"  # Data
record = {"name": "John", "course": "IT", "marks": 80}  # Record
file = [record]  # File (collection of records)

print("Data:", data)
print("Record:", record)
print("File:", file)

# 2. DATA STRUCTURE CLASSIFICATION

print("\n=DATA STRUCTURE CLASSIFICATION ")

"""
1. Primitive Data Structures
2. Linear Data Structures
3. Non-Linear Data Structures
"""

# Primitive
integer_value = 10
float_value = 3.5
char_value = "A"
boolean_value = True


# 3. LINEAR DATA STRUCTURES

print("\n=ARRAY")

# Array (List in Python)
marks = [50, 60, 70, 80, 90, 100]

# Traversing
total = 0
for mark in marks:
    total += mark

average = total / len(marks)
print("Average Marks:", average)

"""
Application:
- Storing student marks
Reason:
- Elements stored in contiguous memory
- Random access using index
"""

print("\n=LINKED LIST")

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Creating linked list
head = Node(10)
second = Node(20)
third = Node(30)

head.next = second
second.next = third

# Traversing linked list
current = head
while current:
    print(current.data)
    current = current.next

"""
Application:
- Memory management
- Dynamic data storage
Reason:
- Stored in non-contiguous memory
"""

print("\n=STACK (LIFO) ")

stack = []

# Insert (Push)
stack.append(10)
stack.append(20)

# Delete (Pop)
print("Popped:", stack.pop())

"""
Application:
- Function calls
- Undo operations
Reason:
- Follows Last-In-First-Out principle
"""


print("\n=QUEUE (FIFO)")

from collections import deque

queue = deque()

# Insert
queue.append(10)
queue.append(20)

# Delete
print("Dequeued:", queue.popleft())

"""
Application:
- CPU scheduling
- Web server request handling
Reason:
- Follows First-In-First-Out principle
"""

# 4. NON-LINEAR DATA STRUCTURES

print("\n=TREE")

class TreeNode:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

root = TreeNode(10)
root.left = TreeNode(5)
root.right = TreeNode(15)

# Inorder Traversal
def inorder(node):
    if node:
        inorder(node.left)
        print(node.data)
        inorder(node.right)

inorder(root)

"""
Application:
- File systems
- Database indexing
Reason:
- Hierarchical parent-child relationship
"""


print("\n=GRAPH")

graph = {
    "A": ["B", "C"],
    "B": ["A", "D"],
    "C": ["A"],
    "D": ["B"]
}

# Traversal using BFS
def bfs(graph, start):
    visited = set()
    queue = deque([start])

    while queue:
        vertex = queue.popleft()
        if vertex not in visited:
            print(vertex)
            visited.add(vertex)
            queue.extend(graph[vertex])

bfs(graph, "A")

"""
Application:
- Social networks
- Artificial Intelligence
- Graphics
Reason:
- Represents relationships between entities
"""

# 5. OPERATIONS ON DATA STRUCTURES

print("\n SEARCHING (Linear Search)")

def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1

print("Index of 80:", linear_search(marks, 80))


print("\n=SORTING (Bubble Sort)")

def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

numbers = [5, 2, 9, 1]
bubble_sort(numbers)
print("Sorted:", numbers)


print("\n=MERGING")

listA = [1, 2, 3]
listB = [4, 5, 6]
listC = listA + listB
print("Merged List:", listC)

# 6. ALGORITHM EXAMPLE

print("\n=ALGORITHM EXAMPLE")

def multiply(x, y):
    z = x * y
    return z

print("Multiplication Result:", multiply(5, 4))


# 7. TIME AND SPACE COMPLEXITY

"""
Time Complexity:
Amount of time needed for algorithm to run.
Example:
Linear Search → O(n)
Binary Search → O(log n)

Space Complexity:
Memory used by algorithm during execution.
Important for large data and multi-user systems.
"""

# 8. HOW DATA STRUCTURES WORK WITHIN SYSTEMS

"""
Operating System:
- Queue → Process scheduling
- Stack → Function calls

Compiler Design:
- Stack → Syntax checking
- Tree → Expression parsing

Artificial Intelligence:
- Graph → Relationship modeling

Graphics:
- Tree/Graph → Scene representation

Web Servers:
- Queue → Handle multiple user requests

Conclusion:
Data Structures organize data.
Algorithms process data.
Together they improve performance and efficiency.
"""

print("\n END OF ASSIGNMENT ")
