# Java Notes
- [Java Notes](#java-notes)
  - [Maps](#maps)
    - [HashMap](#hashmap)
    - [HashMap Iteration](#hashmap-iteration)
    - [HashSet Iteration](#hashset-iteration)
  - [TreeMap](#treemap)
    - [Basic TreeMap](#basic-treemap)
    - [TreeMap with Comparator (Ascending)](#treemap-with-comparator-ascending)
  - [Sets](#sets)
    - [HashSet Initialization](#hashset-initialization)
    - [TreeSet](#treeset)
  - [Lists and Arrays](#lists-and-arrays)
    - [Primitive Array](#primitive-array)
    - [Java Loop Through Array](#java-loop-through-array)
    - [Fixed Size List](#fixed-size-list)
    - [Mutable List](#mutable-list)
    - [List Add All](#list-add-all)
    - [Sublist](#sublist)
    - [2D Array in Java](#2d-array-in-java)
    - [LinkedList](#linkedlist)
    - [Sort an ArrayList](#sort-an-arraylist)
    - [Sort a Primitive Array](#sort-a-primitive-array)
    - [List to a Primitive Array](#list-to-a-primitive-array)
  - [Strings](#strings)
    - [String Manipulation](#string-manipulation)
    - [Sort a String](#sort-a-string)
    - [Loop Through a String](#loop-through-a-string)
    - [Java Regex](#java-regex)
    - [String from char array](#string-from-char-array)
    - [String is a number](#string-is-a-number)
    - [String to an Integer](#string-to-an-integer)
    - [char to an Int](#char-to-an-int)
    - [String from a List](#string-from-a-list)
  - [Priority Queue](#priority-queue)
    - [Basic Priority Queue](#basic-priority-queue)
    - [Priority Queue with Comparator in Ascending Order](#priority-queue-with-comparator-in-ascending-order)
  - [Deque](#deque)
    - [Java Stack (Deque)](#java-stack-deque)
    - [Java Queue (Deque)](#java-queue-deque)
    - [Convert Deque to a String](#convert-deque-to-a-string)

## Maps
### HashMap
```java
Map<String, String> myMap = new HashMap<>();
myMap.put("testKey1","testVal1");
myMap.put("testKey2","testVal2");
myMap.put("testKey2","testVal2");

myMap.get("testKey1");

myMap.containsKey("testKey1");

myMap.remove("testKey1");
```

### HashMap Iteration
```java
Map<String, String> myMap = new HashMap<>();

for (Map.Entry<String, String> myEntry : myMap.entrySet()) {
    myEntry.getKey();
    myEntry.getValue();
}
```

### HashSet Iteration
```java
Set<String> mySet = new HashSet<>();

for (String myString : mySet) {
    System.out.println(myString);
}
```

## TreeMap

### Basic TreeMap
```java
TreeMap<Integer, Integer> myTreeMap = new TreeMap<>();
myTreeMap.put(1, 1);
myTreeMap.put(2, 2);
myTreeMap.put(3, 3);

Map.Entry<Integer, Integer> myFirstEntry = myTreeMap.firstEntry();
Map.Entry<Integer, Integer> myTreeMap = myTreeMap.lastEntry();


myTreemap.remove(1);
```

### TreeMap with Comparator (Ascending)
```java
// The comparators compare the "values"
TreeMap<Integer, Integer> myTreeMap = new TreeMap<>((a, b) -> a - b);

// or

TreeMap<Integer, Integer> myTreeMap = new TreeMap<>(new Comparator<Integer>() {
  public int compare(Integer a, Integer b) {
    return a - b;
  }
});
```

## Sets
### HashSet Initialization
```java
Set<Integer> mySet = new HashSet<>();

mySet.add(1);
mySet.contains(1);

mySet.remove(1);
```

### TreeSet
```java
TreeSet<Integer> myTreeSet = new TreeSet<>((a, b) -> b - a);
myTreeSet.add(5);
myTreeSet.add(2);
myTreeSet.add(3);
myTreeSet.add(1);
myTreeSet.add(4);

myTreeSet.pollFirst(); 
myTreeSet.pollLast();

for(int i : myTreeSet) {
  System.out.println(i);
}
```

## Lists and Arrays

### Primitive Array
```java
int[] myIntArray = new int[5];

int[] myIntArray2 = new int[]{3,2,5,4,1};
```

### Java Loop Through Array
```java
// String array myArray
String[] myArray = new String[]{"foo", "bar"};

for (String myArrayVal : myArray) {
    System.out.println(myArrayVal);
}
```

### Fixed Size List
```java
List<String> myList = Arrays.asList("foo", "bar");
// or
List<String> myList = Arrays.asList(new String[]{"foo", "bar"});
```

### Mutable List
```java
List<String> myList = new ArrayList<>(Arrays.asList("foo", "bar"));

myList.add("baz");

myList.get(0);

myList.remove(0);

myList.size();
```

### List Add All
```java
List<Integer> myList1 = new ArrayList<>();
List<Integer> myList2 = new ArrayList<>();

myList1.addAll(myList2);
```

### Sublist
```java
List<String> myList = new ArrayList();

List<String> mySublist = myList.subList(indexInclusive, indexExclusive);
```

### 2D Array in Java
```java
// Every value is initialized to 0
int[][] my2DIntArray = new int[5][5];
```

### LinkedList

```java
LinkedList<String> myLL = new LinkedList<>();;

myLL.add("foo");

myLL.addFirst("bar");

myLL.addLast("baz");

String myStr0 = myLL.get(0);
String myStr1 = myLL.get(1);

for (String myStr : myLL) {
    // myStr
}

myLL.poll();
myLL.pop();

myLL.pollFirst();
myLL.popFirst();

myLL.pollLast();
```

### Sort an ArrayList
```java
List<Integer> myList = Arrays.asList(1,2,3,4);

Collections.sort(myList);

// reverse order

Collections.sort(myList, Collections.reverseOrder());
```

### Sort a Primitive Array
```java
int[] myArray = new int[]{1,2,3,4,5};

Arrays.sort(myArray);
```

### List to a Primitive Array
```java
// Strings
List<String> myList = Arrays.asList("a","b","c");
String[] myArry = myList.toArray(String[]::new)

List<Integer> myIntList = Arrays.asList(1,2,3);
int[] myIntArr = myIntList.stream().mapToInt(Integer::intValue).toArray();
```

## Strings
### String Manipulation
```java

String myString = new String("foo");

char myString_ch = myString.charAt(0);

boolean myStringContains = myString.contains("fo"); // true

String myString2 = "foo" + "bar"; // "foo bar"

String formattedString = String.format("%s::%s", myString1, myString2);

String mySubstring = myString.substring(indexInclusive, indexExclusive);

int myStringLen = myString.length();

String[] mySplitString = myString.split("o");

```

### Sort a String
```java
String myString = "foobar"

Arrays.sort(myString.toCharArray());

String mySortedString = new String(myString);
```

### Loop Through a String
```java
String myString = "foobar";

for (char c : myString.toCharArray()) {
    // do stuff with
}

// or

for (int i = 0; i < myString.length(); i++) {
    char c = myString.charAt(i);
}

// or 

for (String s : myString.split("")) {
  // s
}
```

### Java Regex
```java

// Match pattern into a string(matcher)

Pattern myPattern = Pattern.compile("foo");
Matcher myMatcher = myPattern.matcher("foofoo");

boolean isFound = myMatcher.find();
```

### String from char array
```java
char[] myCharArray = new char[]{'f', 'o', 'o'};
String myString = new String(myCharArray); // "foo"
```

### String is a number 
```java
NumberUtils.isParsable("35.5") 
```

### String to an Integer
```java
String myString = "1";
try{
  Integer.parseInt(myString);
  // Is an integer  
} catch (NumberFormatException e) {
  // Is not an integer
}
```


### char to an Int
```java
char myChar = '1';
Character.getNumericValue(myChar);
```

### String from a List
```java
List<String> myList = new ArrayList<>();

String myString = String.join("", myList);
```

## Priority Queue

### Basic Priority Queue
```java
PriorityQueue<Integer> myPriorityQueue = new PriorityQueue<>();

myPriorityQueue.add(1); // log(n)
myPriorityQueue.poll(); // log(n)
myPriorityQueue.remove(1); // n
```

### Priority Queue with Comparator in Ascending Order
```java
PriorityQueue<Integer> myPriorityQueue = new PriorityQueue<>(new Comparator<Integer>(){
  public int compare(Integer a, Integer b) {
    return a - b
  }
});

// OR
PriorityQueue<Integer> myPriorityQueue = new PriorityQueue<>((a, b) -> a - b); // ascending
```

## Deque

### Java Stack (Deque)
``` java
Deque<Integer> myStack = new ArrayDeque<>();

myStack.addLast(1);
myStack.addLast(2);
myStack.addLast(3);

myStack.peekLast(); // 3

myStack.removeLast(); // 3
myStack.removeLast(); // 2
myStack.removeLast(); // 1
```

### Java Queue (Deque)
``` java
Deque<Integer> myQueue = new ArrayDeque<>();

myQueue.addLast(1);
myQueue.addLast(2);
myQueue.addLast(3);

myQueue.peekFirst(); // 1

myQueue.removeFirst(); // 1
myQueue.removeFirst(); // 2
myQueue.removeFirst(); // 3
```

### Convert Deque to a String
```java
Deque<Integer> myStack = new ArrayDeque<>();

myStack.addLast(1);
myStack.addLast(2);
myStack.addLast(3);

String myString = myStack.stream().map(String::valueOf).collect(Collectors.joining("")); // "123"

```