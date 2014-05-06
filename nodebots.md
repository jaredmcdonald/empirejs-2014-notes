# nodebots

- DOM animation: alter the apperance or position of an element by modifying the value of a style property over a given interval
- Canvas animation: redrawing at a given interval

etc.

This all applies to animating nodebots. We need fine-grained, frame-by-frame control.

**Problem space**: complex, coordinated servo animations.

Servo - just a little motor with a limited motion from 0 to 180 degrees. Without fine-grained control they are very jerky.

Solution: *frame-constrained servo movement*

Additionally, there's a complexity problem:

"Degrees of freedom", or "DOF" - more freedom, more complexity
