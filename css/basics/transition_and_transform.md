# Transition
Human eyes love slow motion change. Image changing color of something slowly or in world life, when the curtain lifts on the stage in slow motion, our eyes love that. Instant change is boring and not easy on eyes. It becomes difficult to process things quickly.

We add animation in the process of changing an elements property.

**NOTE: Not all properties are transition-able.**

Usage

```css
div {
    width: 200px;
    height: 100px;
    background-color: yellow;
    transition: background-color 0.5s ease; 
    /*
    (propety_to_transtion, delay_before_completion, specify_speed_at_starting_and_ending_of_transition)
    */
}

div:hover {
    background-color: lightblue;
}
```


# Transform
This property allow us to rotate elements as we wish.
