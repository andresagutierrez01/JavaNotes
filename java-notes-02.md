# Java Notes

- [Java Notes](#java-notes)
  - [PriorityQueue](#priorityqueue)
  - [Queue](#queue)
  - [Stack](#stack)
  - [Sorting](#sorting)
    - [Arrays.sort()](#arrayssort)
    - [Collections.sort()](#collectionssort)
  - [List / Array Conversions](#list--array-conversions)
    - [int\[\] -\> List\<Intege\\r\>](#int---listinteger)
    - [List\<Integer\> -\> int\[\]](#listinteger---int)
    - [2d List to int\[\]\[\]](#2d-list-to-int)
  - [ImmutableMap](#immutablemap)


## PriorityQueue
```java
PriorityQueue<Integer> pq = new PriorityQueue<>(); // ascending (default)

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> a - b); // ascending

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> b - a);

pq.add(1);
pq.poll();
pq.remove(); // <- This will throw an exc if empty
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
### Arrays.sort()
```java
// Sorting a primitive array
int[] arr = new int[]{3, 5, 1, 6, 2};

Array.sort(arr);

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
