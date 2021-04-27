# Layouts
1. BorderLayout
2. FlowLayout

## BorderLayout
- This is the default layout for frames.

```java
frame.add(testPanel, BorderLayout.WEST);
// NORTH, SOUTH, WEST, EAST, CENTER
```

<div style="text-align: center;">
  <img src="https://i.imgur.com/ff2BO0Z.png" width="200">
</div>


## FlowLayout
- This layout responsively positions the elements and elements only take up space as they require.

```java
testFrame.setLayout(new FlowLayout());
```

## Layout methods
```java
frame.pack(); // makes the window wider as the elements
```
