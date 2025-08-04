# Sequence Diagram Style Guide

As you will create many sequence diagrams in this class, we've compiled this style guide to help your diagrams be correct and accurate.

We recommend that you use Draw.io to create your diagrams, but any diagram that is clear and legible will be accepted. **Illegible diagrams will not be accepted.**

## Common Mistakes

### Organization

Time flows downward on a sequence diagram, so method calls that happen later should appear below calls that happen earlier. This also applies to Objects, if an object is created during a sequence it should appear below the objects that existed before it was created. Objects should be ordered left to right in the order they are first referenced, inasmuch as it keeps the diagram organized. The exception would be an object that is referenced multiple times by various objects in a sequence. This object can be moved to the right of the last object that references it.

### Object Instantiation

If an object is created as part of a sequence, usually with the new() function, there should be an arrow from the Activation Frame of the method that called new pointing to the name box of the created object. This name box should be placed according to the Organization section. If the created object has method calls in its constructor, an Activation Frame will start immediately below the name box.

### Missing Actor/Inciting Function

EVERY sequence diagram starts with some function being called from outside the sequence. This is typically input from an Actor, or a call from an external system to the sequence. This is represented with an arrow with a black circle on the left side to indicate that the calling object is unknown or irrelevant to the sequence.

If you include an Actor, you need to remember that they are NOT an object, thus they do not have a lifeline or activation frames.

### Abstract classes and Interfaces

Sequence diagrams are exclusively concerned with concrete classes, so abstract classes and interfaces should be replaced with their concrete implementation whenever present in the program.

### Missing Activation Frames and Lifelines

EVERY method call needs an activation frame.

EVERY object needs a lifeline.

### Stacked Activation Frames

Whenever an object in a program calls a method on itself, there should be a stacked activation frame for the new method just as though it had been called on a new object. An easy way to determine if a stacked frame is needed is to first give each method its own object, then collapsing the sequence whenever a duplicate object is found.

### Activation Frame Termination

It is important to understand the difference between when an object is Active and when it is Alive. The Lifeline (Vertical dashed line) indicates if the object is Alive, and the Activation Frame (Vertical rectangle) indicates when the object is actively being interacted with. In asynchronous programs there will be times where the object is Alive, but not Active, as it waits for a callback function. This is represented by a gap between the activation frames of the triggering method and the callback method.

### Method calls, Return lines, and Activation Frames

Method call and Return lines are NOT allowed to cross Activation Frames. Typically if one crosses it indicates a problem with your sequence, either that an object is being considered Active when it is not, or because the diagram is improperly spaced. If there is an instance where the diagram would need to cross an activation frame, the line should go around the frame, not through it.

### Method calls vs Return lines vs Callback

Method calls and Callback functions are solid lines, typically a method call goes from left to right and a callback goes from right to left. A return is a dashed line that typically goes from right to left.

### Proper Method Calls

Method call lines should include the method name called by the left object on the right object. This requires that the right object has the specified method and that the left object has access to the right object. You should NOT just put a vague description of what is happening.

### Missing Method calls or Incorrect Sequence

We expect you to be fairly detailed in your diagrams, as well as diagraming what happens in the program correctly. If you skip important method calls, Objects, or call Methods on incorrect Objects you will be docked points.

### System Separation

In M3 and M4 your program will cross notable boundaries with AWS. You can represent this system separation by putting the service in a box, have the callout method point into this box, then the call-in method leave the box to connect to the sequence on the other side. An example of this is present on the M3 sample diagram.

### Method Arguments

Method arguments are required, but typically should just be the datatype of the value being passed. Typically any primitive type objects can be ignored.

## Optional Considerations

### Conditionals

Conditionals are not expected in this class as we only expect to see the positive outcome diagramed. If you chose to include a conditional frame your diagram will still need to be fully legible and correct according to the program.

### Containers and DTOs

Any object that does not have a method called on it other than new, setters, and getters, do not need to be included in sequence diagrams.