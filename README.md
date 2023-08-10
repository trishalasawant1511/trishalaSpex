# Drawing Package Console Application
This is a Visual Studio Console Application that simulates a drawing package. The application allows the addition of various widgets (drawing primitives) to a virtual drawing, specifying their location and size/shape. The supported widgets are:

Rectangle
Square
Ellipse
Circle
Textbox

## Requirements and Assumptions
The application is a console-based simulation, so there is no actual rendering of the widgets.
Widgets are hard-coded within the Main() method.
Integer units are used for all dimensions.
Widths, heights, and diameters of widgets are assumed to be positive values.
The textbox widget only requires specifying the text to be displayed (alignment, font face, and size are not considered).
There is no user input handling as it is not part of the exercise.
The application should be designed following SOLID principles, maintaining good programming practices such as Maintainability, Extensibility, Robustness, Testability, and adhering to SOLID principles.
The application should be able to print out the current drawing by displaying key details of each widget (type, location, and size/shape) to the console.

## Design Decisions
The application follows SOLID principles:

Single Responsibility Principle (SRP): Each class is responsible for a single type of widget and its properties.
Open/Closed Principle (OCP): The application is open for extension (adding new widgets) but closed for modification.
Liskov Substitution Principle (LSP): Subclasses (widgets) can be used interchangeably with the base class (IWidget).
Interface Segregation Principle (ISP): The IWidget interface only contains the necessary methods for all widgets to implement.
Dependency Inversion Principle (DIP): The high-level modules (Main) do not depend on low-level modules (widgets); both depend on abstractions (IWidget).
The application uses an interface, IWidget, to represent the common properties and behavior of all widgets. This ensures that each widget class adheres to the same contract, allowing for easy extensibility.

The widget classes (Rectangle, Square, Ellipse, Circle, and Textbox) implement the IWidget interface, providing specific details for each type of widget.

The Main method contains the hard-coded widget instances, which are then passed to the PrintWidgets function for display.

## Further Work
Given more time, the following improvements could be considered:

Implementing unit tests to ensure the correctness of the widget classes and the PrintWidgets function.

Creating a graphical rendering engine to visualize the drawn widgets on a canvas or using an external library for visualization.

Utilizing design patterns like the Factory Pattern for creating widgets or the Command Pattern for executing actions on them, especially if the application grows in complexity.

Overall, this console application serves as a starting point for a drawing package that adheres to SOLID principles and demonstrates good programming practices. With further enhancements, it can become a fully-fledged drawing application with additional features and rendering capabilities.
