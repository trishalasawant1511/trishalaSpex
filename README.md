# Demonstration of SOLID principles - SpreadEX
SpreadEXTrishala is a project that demonstrates object-oriented programming in C# and also the usage of shapes, formatting, and console printing. While the current implementation is functional and tested, there are several opportunities for improvement to enhance maintainability, flexibility, and overall code quality.
This README document explains the design decisions made and outlines possible improvements that could be made with more time.

## Task Definition
To develop a Visual Studio Console Application that simulates a drawing package. The application allows the addition of various widgets (drawing primitives) to a virtual drawing, specifying their location and size. The 5 drawing primitives (widgets) are:
1. Rectangle
2. Square
3. Ellipse
4. Circle
5. Textbox

## Requirements and Assumptions
1. The application is a console-based simulation, so there is no actual rendering of the widgets.
2. Widgets are hard-coded within the Main() method.
3. Integer units are used for all dimensions.
4. Widths, heights, and diameters of widgets are assumed to be positive values.
5. The textbox widget only requires specifying the text to be displayed (alignment, font face, and size are not considered).
6. There is no user input handling as it is not part of the exercise.
7. The application should be designed following SOLID principles, maintaining good programming practices such as Maintainability, Extensibility, Robustness, Testability, and adhering to SOLID principles.
8. The application should be able to print out the current drawing by displaying key details of each widget (type, location, and size/shape) to the console.

## Design Decisions
The application follows
1. **Single Responsibility Principle (SRP)**: Each class is responsible for a single type of widget and its properties.
2. **Open/Closed Principle (OCP)**: The application is open for extension (adding new widgets) but closed for modification.
3. **Liskov Substitution Principle (LSP)**: Subclasses (widgets) can be used interchangeably with the base class (BaseWidget).
4. **Interface Segregation Principle (ISP)**: The BaseWidget interface only contains the necessary methods for all widgets to implement that is to represent the common properties and behavior of all widgets. This ensures that each widget class adheres to the same contract, allowing for easy extensibility.
5. **Dependency Inversion Principle (DIP)**: The high-level modules (Main) do not depend on low-level modules (widgets); both depend on abstractions (BaseWidget).
6. **Formatting with Delegates**: The BaseWidget class utilizes delegate-based formatting for each shape type, allowing custom-formatted details to be generated.
7. **ConsoleWidgetPrinter**: The application uses a separate class for printing (ConsoleWidgetPrinter) because any changes to widgets that are adding any additional widgets or customizing any current widget won't make it necessary to make a change in the console printing class. The Main method contains the hard-coded widget instances, which are then passed to the PrintWidgets function for display.
8. **Test-Driven Development (TDD)**: Test cases have been written using xUnit to ensure the correctness of the code. The tests cover various scenarios, including shape details, formatting, and console printing.

## Further Work
Given more time, the following improvements could be considered:
1. **Separation of Concerns**: The current implementation mixes formatting logic with printing logic. Consider separating these concerns into distinct classes to improve maintainability and testability.
2. **Dependency Injection**: Instead of directly instantiating shapes in the Main method, consider using dependency injection to provide the shapes to the Program class. This improves flexibility and testability.
3. **Error Handling**: The current code assumes that everything will work as expected. It would be beneficial to add proper error-handling mechanisms, such as try-catch blocks, to handle exceptions gracefully.
4. **Better Console Handling**: The reliance on console output in tests can be improved by using interfaces and dependency injection for console-related operations, enabling easier testing.
5. **More Extensive Testing**: While the provided test cases cover various scenarios, adding more edge cases, boundary conditions, and negative tests can further enhance the test coverage
6. **Code Documentation**: Adding XML comments and code documentation would help other developers understand the purpose and usage of various classes, methods, and properties.
7. **Code Refactoring**: The codebase can be refactored to adhere to SOLID principles and achieve better code organization, making it more maintainable and extensible.
8. **Graphical rendering engine**: Creating a graphical rendering engine to visualize the drawn widgets on a canvas or using an external library for visualization. Utilizing design patterns like the Factory Pattern for creating widgets or the Command Pattern for executing actions on them, especially if the application grows in complexity.

In conclusion, this console application serves as a starting point for a drawing package that adheres to SOLID principles and demonstrates good programming practices. With further enhancements, it can become a fully-fledged drawing application with additional features and rendering capabilities.
