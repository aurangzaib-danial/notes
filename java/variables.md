# Variables

## Main types
1. int
2. double (large decimal points)
3. float 
4. char (single character)
5. boolean
6. String
7. long (large integers)

## Declaration
```java
String name = 'Sunny';
int students = 10;
double the_pi = 3.14;
```

## Typecasting
We cannot set the type of a variable to another type by setting a new value. However, we can change the type of a value.

```java
double pi = 3.14;
int whole_pi = (int) pi;
```

## Scope
- Only limited to methods. No fancy leakage.

## Class constants
```java
public class Greeting {
  private static final double pi = 3.14;
  // use this variable anywhere inside the class
}
```

## Primitive types
Primitive types are always initialized with a value. 

```java
int number;
number //=> 0
boolean question;
question //=> false
```
**String** is not a primitive type in Java so a **String** varible's value is set to **null** if its not defined.
