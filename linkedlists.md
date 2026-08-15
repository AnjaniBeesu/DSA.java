# Linked Lists 
# Table of Contents
1. What is a Linked List?
2. Why use Linked Lists?
3. Advantages & Disadvantages
4. Types of Linked Lists
5. Node Structure
6. Common Operations
7. Time Complexities
8. Functions to Know
9. Real World Uses
10. Interview Questions
11. Coding Patterns
12. Common Mistakes
13. Cheat Sheet

---

# What is a Linked List?

A Linked List is a linear data structure where elements (nodes) are stored in separate memory locations.

Each node contains:

- Data
- Pointer(s) to another node

Unlike arrays, linked lists are **not stored in contiguous memory**.

Example:

```
10 -> 20 -> 30 -> 40 -> NULL
```

---

# Why Linked Lists?

Arrays have fixed size and expensive insertions/deletions.

Linked Lists provide:

- Dynamic memory allocation
- Easy insertion
- Easy deletion
- No shifting of elements

---

# Node Structure

## C

```c
struct Node{
    int data;
    struct Node* next;
};
```

---

## Java

```java
class Node{
    int data;
    Node next;

    Node(int data){
        this.data=data;
        next=null;
    }
}
```

---

# Types of Linked Lists

## 1. Singly Linked List

Each node points to next node.

```
10 -> 20 -> 30 -> NULL
```

Uses

- Stacks
- Hash chaining
- Graph adjacency list

Pros

- Simple
- Less memory

Cons

- Cannot traverse backwards

---

## 2. Doubly Linked List

Each node has previous and next pointers.

```
NULL <- 10 <-> 20 <-> 30 -> NULL
```

Uses

- Browser history
- Undo/Redo
- Music playlist

Pros

- Traverse both directions
- Easy deletion

Cons

- Extra memory

---

## 3. Circular Linked List

Last node points back to first.

```
10 -> 20 -> 30
^            |
|____________|
```

Uses

- CPU Scheduling
- Multiplayer games
- Circular queues

Pros

- No NULL pointer
- Continuous traversal

---

## 4. Circular Doubly Linked List

```
10 <-> 20 <-> 30
^              |
|______________|
```

Uses

- Image viewers
- Navigation systems

---

# Advantages

- Dynamic size
- Easy insertion
- Easy deletion
- Efficient memory allocation
- No shifting

---

# Disadvantages

- Sequential access
- Extra memory for pointers
- Cache unfriendly
- Reverse traversal impossible in singly LL

---

# Time Complexity

| Operation | Array | Linked List |
|-----------|-------|-------------|
| Access | O(1) | O(n) |
| Search | O(n) | O(n) |
| Insert Beginning | O(n) | O(1) |
| Insert End | O(1)* | O(n) |
| Delete Beginning | O(n) | O(1) |
| Delete End | O(1)* | O(n) |

*If extra space/end pointer exists.

---

# Important Functions

## Insert

### Beginning

```
new.next=head
head=new
```

Time

```
O(1)
```

---

### End

Traverse until NULL.

```
last.next=new
```

Time

```
O(n)
```

---

### At Position

- Traverse
- Adjust pointers

Time

```
O(n)
```

---

# Delete

## Beginning

```
head=head.next
```

Time

```
O(1)
```

---

## End

Traverse to second last node.

```
secondLast.next=NULL
```

Time

```
O(n)
```

---

## Delete by Value

- Search node
- Change links

Time

```
O(n)
```

---

# Traversal

```
temp=head

while(temp!=null){
    print(temp.data);
    temp=temp.next;
}
```

Time

```
O(n)
```

---

# Searching

Linear search only.

Time

```
O(n)
```

---

# Reverse Linked List

Three pointers

```
prev
curr
next
```

Algorithm

```
next=curr.next
curr.next=prev
prev=curr
curr=next
```

Time

```
O(n)
```

Space

```
O(1)
```

---

# Middle of Linked List

Fast & Slow pointers

```
slow=head
fast=head

slow+=1
fast+=2
```

When fast reaches end

```
slow is middle
```

Time

```
O(n)
```

---

# Detect Cycle

Floyd's Cycle Detection

Also called

- Hare and Tortoise Algorithm

```
slow=head
fast=head

slow=slow.next
fast=fast.next.next
```

If

```
slow==fast
```

Cycle exists.

Time

```
O(n)
```

Space

```
O(1)
```

---

# Merge Two Sorted Lists

Use

- Dummy node
- Compare values
- Append smaller node

Time

```
O(n+m)
```

---

# Find nth Node From End

Method 1

Count length.

Method 2

Two pointers.

Move first pointer n steps.

Move both together.

---

# Remove Duplicates

Sorted LL

Compare adjacent nodes.

Unsorted LL

Use HashSet.

---

# Intersection of Two Lists

Methods

- HashSet
- Two pointer switching

Time

```
O(n)
```

---

# Palindrome Linked List

Methods

- Stack
- Reverse second half
- Compare

---

# Merge Sort on Linked List

Steps

1. Find middle
2. Split
3. Merge recursively

Time

```
O(n log n)
```

---

# Real World Applications

## Browser

Back and Forward

(Doubly LL)

---

## Music Player

Previous song

Next song

(Doubly LL)

---

## Undo Redo

Editors

(Doubly LL)

---

## LRU Cache

Uses

- HashMap
- Doubly Linked List

---

## Operating Systems

Round Robin Scheduling

(Circular LL)

---

## Memory Management

Free memory lists

---

## Graphs

Adjacency Lists

---

## Blockchain (Conceptually)

Linked blocks

---

# Common Interview Questions

## Easy

- What is Linked List?
- Array vs Linked List
- Advantages?
- Disadvantages?
- Types of Linked Lists
- Why use Doubly LL?
- Why use Circular LL?
- How is memory allocated?
- Why random access impossible?
- Difference between node and pointer?

---

## Medium

- Reverse Linked List
- Middle Node
- Detect Cycle
- Delete nth Node
- Merge Sorted Lists
- Remove Duplicates
- Find Intersection
- Find Loop Length
- Rotate Linked List
- Swap Nodes

---

## Hard

- Flatten Linked List
- Clone Linked List with Random Pointer
- Reverse Nodes in K Groups
- Merge K Sorted Lists
- LRU Cache
- LFU Cache
- Copy List with Random Pointer
- Add Two Numbers
- Sort Linked List
- Partition List

---

# Coding Patterns

## Dummy Node

Useful for

- Merge
- Delete
- Insert

---

## Two Pointer

Used in

- Middle
- Cycle
- nth from end

---

## Fast Slow Pointer

Used in

- Palindrome
- Middle
- Cycle Detection

---

## Hashing

Used in

- Duplicate removal
- Cycle detection
- Intersection

---

## Recursion

Used in

- Reverse
- Merge Sort
- DFS style problems

---

# Common Mistakes

- Forgetting NULL checks
- Losing head pointer
- Wrong pointer update order
- Infinite loops
- Memory leaks (C/C++)
- Forgetting to update tail
- Off-by-one errors

---

# Top LeetCode Problems

Easy

- Reverse Linked List
- Merge Two Sorted Lists
- Linked List Cycle
- Middle of Linked List
- Remove Duplicates

Medium

- Add Two Numbers
- Remove nth Node From End
- Reorder List
- Odd Even Linked List
- Rotate List
- Sort List
- Swap Nodes in Pairs
- Partition List

Hard

- Reverse Nodes in K Group
- Merge K Sorted Lists
- Copy List with Random Pointer
- LFU Cache
- LRU Cache

---

# Quick Revision

✔ Node = Data + Pointer

✔ Dynamic Size

✔ No Random Access

✔ Insert/Delete = Efficient

✔ Search = O(n)

✔ Reverse = Three Pointers

✔ Middle = Fast & Slow

✔ Cycle = Floyd Algorithm

✔ Merge = Dummy Node

✔ Doubly LL = Browser History

✔ Circular LL = CPU Scheduling

✔ LRU Cache = HashMap + Doubly LL

✔ Merge Sort = Best sorting for Linked Lists

---

# Interview Tips

1. Always draw the linked list before coding.
2. Track pointer updates carefully.
3. Check edge cases:
   - Empty list
   - Single node
   - Two nodes
   - Head deletion
   - Tail deletion
4. Prefer iterative solutions unless recursion is required.
5. State the time and space complexity after solving.
