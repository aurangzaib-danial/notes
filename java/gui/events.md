## Events
We need to implement `ActionListener` interface for using commons events like clicking etc.

```java
public class TestGui implements ActionListener {
  private JButton fooButton = new JButton("foo button");
  public void buttonTest() {
    fooButton.addActionListener(this);
    // We need to attach ActionListener to the object and also pass the Gui instance because it needs to know which actionPerformed method to call
  }
  @Override // this keywords simply means that we are overriding the interface method.
  public void actionPerformed(ActionEvent e) {
    if (e.getSource == fooButton) {
      // run code
    }
  }
}
```
