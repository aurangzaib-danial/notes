# Strings
## Methods
```java
String name = "Harry";
name.length();

// getting a character
char firstLetter = name.charAt(0);

// silicing a part from string
firstTwoLetters = name.substring(0, 2);
// 0 is the start
// 2 is the end. However, the character on index 2 is not included.
```

## String comparison is special
```java
string1 == string2 // compares objects id's and not the content

string1.equals(string2) // compares strings content

ClassName.equals(string1, string2) // We can use static methd 
```

## Lexographical (alphabetical order) comparison
```java
string1.compareTo(string2) < 0 
```
Further info
![Lexographical comparison](https://i.imgur.com/0t1Cfq8.png)

