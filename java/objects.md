# Objects
```java
public class Person {
  // class is a factory
  public static void listPersons{
    // class method when we add the keyword static
  }
  
  private String name;
  private String address;
  private int age;
  // above are properties of the object
  
  public Person(String name, String address, int age) {
    // method named after the class is the constructor method
    this.name = name;
    this.address = address;
    this.age = age;
  }

  public greet() {
    // instance method
  }
}
```

## Abstract class
```java
public abstract class  ApplicationController {
  // abstract class is only used as a parent and we do not need instances of it.
}
```

## toString method for objects
- Every object in Java has a toString method. 
- This method is useful for printing information about the object. 
- If we do not overwrite this method then for non-primitive types, the location of the object in the memory is returned which is not very useful.

## this keyword
```java
public class Dog {
  private String name;
  public void setName(name) {
    this.name = name; // this keyword gives us reference to the object
  }
}
```







