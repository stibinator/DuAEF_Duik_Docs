## Kleaner

The "Kleaner" is a tool to automatically clean the selected animations.  
It removes unnecessary keyframes (keyframes which do not result in any animation), and generates and controls anticipations, interpolations and follow-through of the animations.

After having removed unnecessarry keyframes, it works with an expression which is controlled by an effect.

### Use

1. Select the keyframes of the animation you want to clean.
2. Click on the "Kleaner" button.

One effect is created for all selected properties of the same layer. That means all properties will be controlled by the same values. If you need different values for several properties, create a new kleaner for each one of them.

### Additionnal Panel

The additionnal panel is divided in three sections corresponding to the three steps of the "Kleaner " process.

- Remove unnecessary keyframes:
  Check or uncheck the checkbox to activate or deactivate this step when you run the "Kleaner"
- Separate Dimensions:
  In case you add the kleaner on multi-dimensionnal properties, you can check this option to separate the dimensions first, and control separately each axis.