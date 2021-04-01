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
```
