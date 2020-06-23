---
id: stacks-queues
title: Stacks & Queues
author: Darren Yao
description: 
prerequisites:
 - Bronze - Data Structures
---

## Additional Reading

 - CPH 4.5
 - [PAPS 3.2 3.3, 3.4, 6.2, 6.3, 6.5](https://www.csc.kth.se/~jsannemo/slask/main.pdf)

## [Stacks](http://www.cplusplus.com/reference/stack/stack/)

A stack is a **Last In First Out** (LIFO) data structure that supports three operations, all in $O(1)$ time. Think of it like a real-world stack of papers (or cards).

### C++

 - `push`: adds an element to the top of the stack
 - `pop`: removes an element from the top of the stack
 - `top`: retrieves the element at the top without removing it

```cpp
stack<int> s;
s.push(1); // [1]
s.push(13); // [1, 13]
s.push(7); // [1, 13, 7]
cout << s.top() << endl; // 7
s.pop(); // [1, 13]
cout << s.size() << endl; // 2
```

### Java

 - `push`: adds an element to the top of the stack
 - `pop`: removes an element from the top of the stack
 - `peek`: retrieves the element at the top without removing it

```java
Stack<Integer> s = new Stack<Integer>();
s.push(1); // [1]
s.push(13); // [1, 13]
s.push(7); // [1, 13, 7]
System.out.println(s.peek()); // 7
s.pop(); // [1, 13]
System.out.println(s.size()); // 2
```

## [Queues](http://www.cplusplus.com/reference/queue/queue/)

A queue is a First In First Out (FIFO) data structure that supports three operations, all in $O(1)$ time. 

### C++

 - `push`: insertion at the back of the queue
 - `pop`, deletion from the front of the queue 
 - `front`: which retrieves the element at the front without removing it.

```cpp
queue<int> q;
q.push(1); // [1]
q.push(3); // [3, 1]
q.push(4); // [4, 3, 1]
q.pop(); // [4, 3]
cout << q.front() << endl; // 3
```

### Java

 - `add`: insertion at the back of the queue
 - `poll`: deletion from the front of the queue
 - `peek`, which retrieves the element at the front without removing it

Java doesn't actually have a `Queue` class; it's only an interface. The most commonly used implementation is the `LinkedList`, declared as follows:

```java
Queue<Integer> q = new LinkedList<Integer>();
q.add(1); // [1]
q.add(3); // [3, 1]
q.add(4); // [4, 3, 1]
q.poll(); // [4, 3]
System.out.println(q.peek()); // 3
```

## [Deques](http://www.cplusplus.com/reference/deque/deque/)

A deque (usually pronounced "deck") stands for double ended queue and is a combination of a stack and a queue, in that it supports $O(1)$ insertions and deletions from both the front and the back of the deque. Not very common in Bronze / Silver.

### C++

The four methods for adding and removing are `push_back`, `pop_back`, `push_front`, and `pop_front`. 

```cpp
deque<int> d;
d.push_front(3); // [3]
d.push_front(4); // [4, 3]
d.push_back(7); // [4, 3, 7]
d.pop_front(); // [3, 7]
d.push_front(1); // [1, 3, 7]
d.pop_back(); // [1, 3]
```

### Java

In Java, the deque class is called `ArrayDeque`. The four methods for adding and removing are `addFirst` , `removeFirst`, `addLast`, and `removeLast`.

```java
ArrayDeque<Integer> deque = new ArrayDeque<Integer>();
deque.addFirst(3); // [3]
deque.addFirst(4); // [4, 3]
deque.addLast(7); // [4, 3, 7]
deque.removeFirst(); // [3, 7]
deque.addFirst(1); // [1, 3, 7]
deque.removeLast(); // [1, 3]
```

## [Priority Queues](http://www.cplusplus.com/reference/queue/priority_queue/)

A priority queue supports the following operations: insertion of elements, deletion of the element considered highest priority, and retrieval of the highest priority element, all in $O(\log n)$ time according to the number of elements in the priority queue. Priority is based on a comparator function. The priority queue is one of the most important data structures in competitive programming, so make sure you understand how and when to use it. 

### C++

```cpp
priority_queue<int> pq;
pq.push(7); // [7]
pq.push(2); // [2, 7]
pq.push(1); // [1, 2, 7]
pq.push(5); // [1, 2, 5, 7]
cout << pq.top() << endl; // 7
pq.pop(); // [1, 2, 5]
pq.pop(); // [1, 2]
pq.push(6); // [1, 2, 6]
```

### Java

In Java, we delete and retrieve the element of **lowest** priority.

```java
PriorityQueue<Integer> pq = new PriorityQueue<Integer>();
pq.add(7); // [7]
pq.add(2); // [7, 2]
pq.add(1); // [7, 2, 1]
pq.add(5); // [7, 5, 2, 1]
System.out.println(pq.peek()); // 1
pq.poll(); // [7, 5, 2]
pq.poll(); // [7, 5]
pq.add(6); // [7, 6, 5]
```

## Problems

(actually go through these and check ...)

### Stack

  - UVa 00514 - Rails
  - UVa 00732 - Anagram by Stack
  - UVa 01062 - Containers

### Queue / Deque 

  - UVa 10172 - The Lonesome Cargo
  - UVa 10901 - Ferry Loading III
  - UVa 11034 - Ferry Loading IV
