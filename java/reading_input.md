## Reading input
We can import `Scanner` class for reading from the console.

```java
import java.util.Scanner;
// util is a package
Scanner in = new Scanner(System.in);
// initalize a Scanner object that will handle all the incoming data stream
// `in` is a variable, name it as anything you like
// do it inside a method

// Get integer input
int bottles = in.nextInt();
// Float
double price = in.nextDouble();

// String
String fullName = in.next();
// Only read one word from the input
String sentence = in.nextLine();
// Until Enter is pressed and does not include the new line character
```
> Whenever .next is called, the console will start waiting for input.

# Validating input
```java
// For a prompt
if (userInput.toLowerCase().equals("yes"))
{
  // do magic
}

// For checking if a number is integer
int luckyNumber = 13;
if (in.hasNextInt() && in.nextInt() == luckyNumber) {
  System.out.println("Luck is with us");
}
```
