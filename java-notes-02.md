# Java Notes

- [Java Notes](#java-notes)
  - [PriorityQueue](#priorityqueue)
  - [TreeMap](#treemap)
  - [Queue](#queue)
  - [Stack](#stack)
  - [Sorting](#sorting)
    - [Arrays.sort()](#arrayssort)
    - [Collections.sort()](#collectionssort)
  - [List / Array Conversions](#list--array-conversions)
    - [int\[\] -\> List\<Integer\>](#int---listinteger)
    - [List\<Integer\> -\> int\[\]](#listinteger---int)
    - [2d List to int\[\]\[\]](#2d-list-to-int)
  - [ImmutableMap](#immutablemap)


## PriorityQueue
```java
PriorityQueue<Integer> pq = new PriorityQueue<>(); // ascending (default)

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> a - b); // ascending

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> b - a); // descending

pq.add(1);
pq.poll();
pq.remove(); // <- This will throw an exc if empty
pq.size();
```

## TreeMap
```java
TreeMap<Integer, Integer> treeMap = new TreeMap<>();

treeMap.pollFirstEntry(); // polls
treeMap.firstEntry(); // retrieves but does not remove

// With a Comparator function (descending)
TreeMap<Integer, Integer> treeMap = new TreeMap<>((a, b) -> b - a);
```

## Queue
```java
Deque<Integer> q = new ArrayDeque<>();

q.addLast();
q.peekFirst();
q.pollFirst();
q.removeFirst(); // Throws an exception if empty
```

## Stack
```java
Deque<Integer> stack = new ArrayDeque<>();

stack.addLast();
stack.peekLast();
stack.pollLast();
stack.removeLast(); // Throws an exception if empty
```

## Sorting
### Arrays.sort()
```java
// Sorting a primitive array
int[] arr = new int[]{3, 5, 1, 6, 2};

Array.sort(arr);

// For 2d arrays, you can pass a comparator function to Arrays.sort()
int[][] arr2 = new int[5][2];

Arrays.sort(arr2, (a, b) -> a[0] - b[0]);

// In order to do more complex sorting operations, we must convert the array to a List
// and use Collections.sort() 

List<Integer> list = Arrays.stream(arr).boxed().toList();

// See below for Collections.sort();
```

### Collections.sort()
```java
/**
 * For Java Lists, Collections.sort() must be used. This actually gives us more options on how
 * to sort our array.
 * */

List<Integer> list = new ArrayList<>();
Collections.sort(list);

// Sort in reverse order

List<Integer> list = new ArrayList<>();
Collections.sort(list, Collections.reverseOrder());
 
```

## List / Array Conversions
> For integer arrays in particular, there is a trick, since we need to convert from int Integer and vice versa.
> 
> Use Integer::intValue to covert from Integer to int
> 
> Use Integer::valueOf to convert from int to Integer
> Alternatively use .boxed()

### int[] -> List\<Integer\>
```java
int[] arr = new int[]{};

List<Integer> list = Arrays.stream(arr).boxed().toList();
List<Integer> list = Arrays.stream(arr).mapToObj(Integer::valueOf).toList();
```

### List\<Integer\> -> int[]
```java
List<Integer> list = new ArrayList<>();

int[] arr = list.stream().mapToInt(Integer::intValue).toArray();
```

### 2d List to int[][]
```java
// List<List<Integer>>
List<List<Integer>> list2d = new ArrayList<>();
int[][] arr2d = list2d.stream().map(r -> r.stream().mapToInt(Integer::valueOf).toArray()).toArray(int[][]::new);

List<int[]> list2d2 = new ArrayList<>();
int[][] arr2d2 = list2d2.stream().toArray(int[][]::new);
```

## ImmutableMap
```java
import com.google.common.collect.*;

Map<Character, Character> myMap = ImmutableMap.of(
    'c', 'c',
    'p', 'p'
);
```
