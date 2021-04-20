# Data structures
## Arrays
- Only one type of data can be stored in an array.
- Array's in java only have fixed length. It's important we specify length for arrays with dummy values, if we want to work with it later.

```java
String [] students = {"Sunny", "Ali", "Hamza"};
int [] evens = {2, 4, 6};

// However, if the an array variable is defined but not initalized we need to do following
String [] students;
students = new String [] {"first", "second"};

// properties
students.length //=> 3

// set a length for an array
int[] evens = new int[10];

// Looping
for (String item : array) {
  System.out.println(item);
}

// multi-dimensional arrays
int [][] collection = {{1,2,3}, {4,5,6}};
// just keep adding square brackets [] for more hierarchy 
```

## Lists
Arrays have a fixed length in Java. To overcome this issue, we use lists.
- These are just like arrays but you can add or delete from them.

```java
import java.util.ArrayList;
import java.util.List;

List<String> students = new ArrayList<>;
students.add("Sunny");
students.add("Mark");
students.get(index); // we can use index as well as the value itself
students.remove("Sunny");
students.set(index, newValue); overwrite value of something
```
