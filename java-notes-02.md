# Java Notes

## PriorityQueue
```java
PriorityQueue<Integer> pq = new PriorityQueue<>(); // ascending (default)

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> a - b); // ascending

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> b - a);

pq.add(1);
pq.poll();
pq.size();
```

## Queue
```java
Deque<Integer> q = new ArrayDeque<>();

q.addLast();

q.peekFirst();

q.removeFirst();
```

## Stack
```java
Deque<Integer> stack = new ArrayDeque<>();

stack.addLast();
stack.peekLast();
stack.removeLast();
```
