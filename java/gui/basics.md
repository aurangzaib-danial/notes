# Graphical User Interface Basics
GUI's in java are mostly built using Java Swing library which is based on Java awt which is an older way to make GUI's. Swing requires awt for some of its functionality.

## Libraries to require
```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
```


## Frames
```java
// A window is a frame object in java
JFrame testFrame = new JFrame("Test Window");
testFrame.setTitle = "New title";
testFrame.setVisible(true) // This is false by default
testFrame.setSize(1000, 500) // width, height
testFrame.dispose() // Close the frame
// on clicking the 'X' button close the frame not hide it. Hiding is the default option.
testFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
```

## Basic elements
```java
JTextField textField = new JTextFeild();
textField.getText();
JLabel testLabel = new JLabel("Placeholder text");

// We need to progressively add elements to the frame
testFrame.add(textField);
testFrame.add(testLabel);


// jPanel is for grouping multiple elements together
JPanel testPanel = new JPanel();
testPanel.add(testField);
testPanel.add(testLabel);

// Now we can just add the testPanel to the frame
testFrame.add(testPanel);
```

## Lists and ComboBox (Selection box)
```java
String[] comboBoxStrings = {"one", "two", "three"};
JComboBox<String> testComboxBox = new JComboBox<String>(comboBoxStrings);

String[] listStrings = {"one", "two", "three"};
JList testList = new JList(listStrings);
```






