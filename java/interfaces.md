# Interfaces
- These are a way to specify an outline of how a class should be designed or what kind of methods it should respond to.
- These are different from a super class as these just specify interface not how methods are implemented.
- The interface is a strict way to enforce a class what kind of interface it should have.

```java
public interface Shape
{
  double area();
  double perimeter();
}

public class Rectangle implements Shape {
  public double area() {
   // implement it's own way 
  }
}

public class Square implements Shape {
  public double area() {
    // implement it's own way
  }
}
```
