
# Stack (LIFO - Last In, First Out)

## What is a Stack?

A **Stack** is a linear data structure that follows the **LIFO (Last In, First Out)** principle.

Think of a stack of plates:

- The last plate placed on top is the first one removed.

---

# Characteristics

- Linear Data Structure
- Follows LIFO Principle
- Insertion and deletion happen only at one end (Top)
- Efficient for recursive and backtracking problems

---

# Operations

| Operation | Description | Time Complexity |
|-----------|-------------|----------------|
| Push | Insert an element | O(1) |
| Pop | Remove the top element | O(1) |
| Peek / Top | View the top element | O(1) |
| isEmpty | Check whether stack is empty | O(1) |
| Size | Number of elements | O(1) |

---

# Stack Representation

```
Push(10)

Top
 ↓
-------
| 10 |
-------

Push(20)

Top
 ↓
-------
| 20 |
-------
| 10 |
-------

Push(30)

Top
 ↓
-------
| 30 |
-------
| 20 |
-------
| 10 |
-------
```

---

# Push Operation

## Algorithm

```
Push(x)

1. Insert x at the top.
2. Update top.
```

Example

```
Before

Top
 ↓
20
10

Push(30)

After

Top
 ↓
30
20
10
```

Time Complexity

```
O(1)
```

---

# Pop Operation

## Algorithm

```
1. Check if stack is empty.
2. Remove top element.
3. Return removed element.
```

Example

```
Before

Top
 ↓
30
20
10

Pop()

After

Top
 ↓
20
10
```

Time Complexity

```
O(1)
```

---

# Peek Operation

Returns the top element without removing it.

```
Top
 ↓
30
20
10

Peek() → 30
```

---

# isEmpty()

```
Stack = []

isEmpty() → true
```

---

# Stack Using Array (Java)

```java
class StackArray {
    int[] stack = new int[100];
    int top = -1;

    void push(int x) {
        stack[++top] = x;
    }

    int pop() {
        return stack[top--];
    }

    int peek() {
        return stack[top];
    }

    boolean isEmpty() {
        return top == -1;
    }
}
```

---

# Stack Using Linked List (Java)

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
    }
}

class StackLL {

    Node top;

    void push(int x) {
        Node node = new Node(x);
        node.next = top;
        top = node;
    }

    int pop() {
        if(top == null)
            return -1;

        int val = top.data;
        top = top.next;
        return val;
    }
}
```

---

# Java Stack (Collections Framework)

```java
import java.util.Stack;

Stack<Integer> st = new Stack<>();

st.push(10);
st.push(20);
st.push(30);

System.out.println(st.peek()); //30
System.out.println(st.pop());  //30
System.out.println(st.empty());//false
```

---

# Applications of Stack

- Function Calls (Call Stack)
- Undo / Redo
- Browser History
- Parentheses Matching
- Expression Evaluation
- DFS Traversal
- Backtracking
- String Reversal
- Syntax Parsing
- Compiler Design

---

# Parentheses Matching

Example

```
Input

{[()]}

Output

Balanced
```

Algorithm

```
For every character

If opening bracket
    Push

Else

Check top

If matching
    Pop

Else
    Not Balanced
```

Time Complexity

```
O(n)
```

---

# Infix, Prefix and Postfix

| Type | Example |
|------|---------|
| Infix | A+B |
| Prefix | +AB |
| Postfix | AB+ |

Example

```
Infix

A+B*C

Prefix

+A*BC

Postfix

ABC*+
```

---

# Next Greater Element

Example

```
Input

[4,5,2,25]

Output

5 25 25 -1
```

Algorithm

- Traverse from right to left.
- Remove smaller elements from the stack.
- Stack top becomes Next Greater Element.

Time Complexity

```
O(n)
```

---

# Largest Rectangle in Histogram

Uses a **Monotonic Stack**.

Example

```
Input

2 1 5 6 2 3

Output

10
```

Time Complexity

```
O(n)
```

---

# Valid Parentheses (LeetCode 20)

```java
public boolean isValid(String s) {

    Stack<Character> st = new Stack<>();

    for(char c : s.toCharArray()) {

        if(c=='(' || c=='{' || c=='[')
            st.push(c);

        else{

            if(st.isEmpty())
                return false;

            char top = st.pop();

            if(c==')' && top!='(') return false;
            if(c=='}' && top!='{') return false;
            if(c==']' && top!='[') return false;
        }
    }

    return st.isEmpty();
}
```

Time Complexity

```
O(n)
```

Space Complexity

```
O(n)
```

---

# Time Complexity Summary

| Operation | Complexity |
|-----------|------------|
| Push | O(1) |
| Pop | O(1) |
| Peek | O(1) |
| Search | O(n) |

---

# Top Stack LeetCode Problems (Interview Favorites)

| LeetCode # | Problem | Difficulty | Pattern |
|------------|---------|------------|---------|
| **20** | Valid Parentheses | Easy | Basic Stack |
| **155** | Min Stack | Medium | Design |
| **225** | Implement Stack using Queues | Easy | Simulation |
| **232** | Implement Queue using Stacks | Easy | Simulation |
| **150** | Evaluate Reverse Polish Notation | Medium | Expression Evaluation |
| **71** | Simplify Path | Medium | Stack |
| **394** | Decode String | Medium | Nested Stack |
| **735** | Asteroid Collision | Medium | Stack Simulation |
| **739** | Daily Temperatures | Medium | Monotonic Stack |
| **496** | Next Greater Element I | Easy | Monotonic Stack |
| **503** | Next Greater Element II | Medium | Monotonic Stack |
| **901** | Online Stock Span | Medium | Monotonic Stack |
| **84** | Largest Rectangle in Histogram | Hard | Monotonic Stack |
| **85** | Maximal Rectangle | Hard | Histogram |
| **42** | Trapping Rain Water | Hard | Stack |
| **856** | Score of Parentheses | Medium | Parentheses |
| **1249** | Minimum Remove to Make Valid Parentheses | Medium | Parentheses |
| **32** | Longest Valid Parentheses | Hard | Parentheses |
| **402** | Remove K Digits | Medium | Monotonic Stack |
| **1475** | Final Prices With a Special Discount | Easy | Monotonic Stack |
| **2104** | Sum of Subarray Ranges | Medium | Monotonic Stack |
| **907** | Sum of Subarray Minimums | Medium | Monotonic Stack |
| **946** | Validate Stack Sequences | Medium | Simulation |
| **456** | 132 Pattern | Medium | Monotonic Stack |
| **1190** | Reverse Substrings Between Each Pair of Parentheses | Medium | Strings + Stack |

---

# Must-Do Problems

- ✅ 20. Valid Parentheses
- ✅ 155. Min Stack
- ✅ 150. Evaluate Reverse Polish Notation
- ✅ 739. Daily Temperatures
- ✅ 496. Next Greater Element I
- ✅ 503. Next Greater Element II
- ✅ 84. Largest Rectangle in Histogram
- ✅ 42. Trapping Rain Water
- ✅ 394. Decode String
- ✅ 735. Asteroid Collision

---

# Pattern-wise Classification

## Basic Stack

- 20. Valid Parentheses
- 155. Min Stack
- 225. Implement Stack using Queues
- 232. Implement Queue using Stacks

## Monotonic Stack

- 496. Next Greater Element I
- 503. Next Greater Element II
- 739. Daily Temperatures
- 901. Online Stock Span
- 907. Sum of Subarray Minimums
- 2104. Sum of Subarray Ranges
- 84. Largest Rectangle in Histogram
- 1475. Final Prices With a Special Discount

## Expression Evaluation

- 150. Evaluate Reverse Polish Notation
- 71. Simplify Path
- 394. Decode String

## Parentheses Problems

- 20. Valid Parentheses
- 32. Longest Valid Parentheses
- 856. Score of Parentheses
- 1249. Minimum Remove to Make Valid Parentheses
- 1190. Reverse Substrings Between Each Pair of Parentheses

## Stack Simulation

- 735. Asteroid Collision
- 946. Validate Stack Sequences
- 456. 132 Pattern

---

# Interview Tips

- Whenever you hear **Next Greater**, **Next Smaller**, **Previous Greater**, or **Previous Smaller**, think **Monotonic Stack**.
- Histogram and Stock Span are classic monotonic stack interview questions.
- Parentheses problems almost always use a stack.
- Practice implementing stacks using both arrays and linked lists before using Java's built-in `Stack` class.
- Always analyze whether a stack solution can reduce a brute-force **O(n²)** approach to **O(n)**.

---

# References

- Data Structures and Algorithms (DSA)
- LeetCode Stack Problems
- Common FAANG Interview Patterns
````
