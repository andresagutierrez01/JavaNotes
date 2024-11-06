# Java Notes

- [Java Notes](#java-notes)
  - [PriorityQueue](#priorityqueue)
  - [Queue](#queue)
  - [Stack](#stack)
  - [Sorting](#sorting)
  - [Convert from primitive arrays to Lists](#convert-from-primitive-arrays-to-lists)


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

## Sorting
```java
// Sorting a primitive array
int[] arr = new int[]{3, 5, 1, 6, 2};

Array.sort(arr);

// Sort in reverse order
// We need to first convert to a List

List<Integer> sorted = Arrays.stream(arr).boxed().collect(Collectors.toList());

Collections.sort(sorted, Collections.reverseOrder());
```

## Convert from primitive arrays to Lists
```java
// Integer
int[] arr1 = new int[]{1,2,3,4,5};
List<Integer> list1 = Arrays.stream(arr1).mapToObj(Integer::valueOf).collect(Collectors.toList());
List<Integer> list2 = Arrays.stream(arr1).boxed().toList();

List<Integer> list3 = new ArrayList<>();
int[] arr2 = list3.stream().mapToInt(Integer::intValue).toArray();
```