
## Building a GUI Framework
1. **Introduction**: Imagine we want to build a framework for creating graphical user interfaces (GUIs). This framework will allow developers to create applications with various UI components like text boxes, check boxes, and drop-down lists.

2. **Common Behaviors**: 
   - All UI components share common behaviors, such as enabling/disabling and resizing based on screen dimensions.
   - **Example**: We can create a base class, `UIControl`, that encapsulates these common behaviors:
     ```java
     public class UIControl {
         private boolean isEnabled;

         public void enable() {
             isEnabled = true;
         }

         public void disable() {
             isEnabled = false;
         }

         public boolean isEnabled() {
             return isEnabled;
         }
     }
     ```

## Inheritance
1. **Creating Derived Classes**: Other UI components will inherit from `UIControl`, allowing them to reuse the common behaviors defined there.
   - **Example**: A `TextBox` class that extends `UIControl`:
     ```java
     public class TextBox extends UIControl {
         private String text;

         public TextBox(String text) {
             this.text = text;
         }

         @Override
         public String toString() {
             return "TextBox: " + text + " (Enabled: " + isEnabled() + ")";
         }
     }
     ```

2. **Hierarchy**: The hierarchy allows us to define components like `CheckBox` and `DropDown` similarly, each inheriting from `UIControl`.


# Understanding the Object Class in Java

## Inheritance from the Object Class
- **Basic Concept**: When we create a class, it implicitly extends the `Object` class unless specified otherwise. This means all classes inherit methods from `Object`, such as `toString()`, `equals()`, and `hashCode()`.
  
- **Example**: Consider the `TextBox` class:
  ```java
  public class TextBox extends UIControl {
      // Additional properties and methods specific to TextBox
  }
  ```
  Here, `TextBox` inherits from `UIControl`, which in turn inherits from `Object`.

## Members of the Object Class
### Common Methods
1. **getClass()**: Returns the runtime class of this object.
   - **Usage**:
     ```java
     TextBox textBox = new TextBox();
     Class<?> clazz = textBox.getClass();
     System.out.println("Class: " + clazz.getName());
     ```

2. **equals(Object obj)**: Determines whether the specified object is equal to this object.
   - **Default Implementation**: The default implementation compares references, not values.
   - **Overriding Example**:
     ```java
     @Override
     public boolean equals(Object obj) {
         if (this == obj) return true;
         if (!(obj instanceof TextBox)) return false;
         TextBox other = (TextBox) obj;
         return this.content.equals(other.content);
     }
     ```

3. **hashCode()**: Returns a hash code value for the object.
   - **Usage**: Used in hash-based collections like `HashMap`.
   - **Example**:
     ```java
     @Override
     public int hashCode() {
         return Objects.hash(content); // Generates a hash based on the content
     }
     ```

4. **toString()**: Returns a string representation of the object.
   - **Overriding Example**:
     ```java
     @Override
     public String toString() {
         return "TextBox with content: " + this.content;
     }
     ```

### Additional Methods
- **notify() and wait()**: Used in multithreading for communication between threads.
  - **Note**: These methods are more advanced topics that we can explore later.


# Understanding Constructors in Java with Inheritance

## Introduction to Constructors
Constructors are special methods used to initialize objects when an instance of a class is created. They have the same name as the class and do not have a return type. I


## Using Constructors with Inheritance
When creating a class hierarchy, constructors play a crucial role in initializing the base class (superclass) before initializing the derived class (subclass).

### Example: UI Control Class
Let's create a framework for building graphical user interfaces (GUIs) where various UI components can inherit common behaviors from a base class.

1. **Defining the Base Class (`UIControl`)**:
   ```java
   public class UIControl {
       private boolean isEnabled;

       public UIControl(boolean isEnabled) {
           this.isEnabled = isEnabled; // Initialize the isEnabled field
       }

       public void enable() {
           isEnabled = true;
       }

       public void disable() {
           isEnabled = false;
       }

       public boolean isEnabled() {
           return isEnabled;
       }
   }
   ```

2. **Creating a TextBox Class**:
   When we create a `TextBox` class that extends `UIControl`, we need to ensure that we properly call the constructor of `UIControl`.
   ```java
   public class TextBox extends UIControl {
       private String content;

       // Constructor for TextBox that also initializes the superclass
       public TextBox(String content, boolean isEnabled) {
           super(isEnabled); // Call the constructor of UIControl
           this.content = content;
       }

       @Override
       public String toString() {
           return "TextBox: " + content + " (Enabled: " + isEnabled() + ")";
       }
   }
   ```

### Compilation Error Example
If the `UIControl` class had a default constructor that required a parameter, we would need to explicitly call that constructor in the `TextBox` constructor. If we forget to do this, we will encounter a compilation error.









## Access Modifiers
1. **Public and Private**:
   - Public members are accessible from anywhere, while private members can only be accessed within the class.
   - **Example**: In a `UIControl` class:
     ```java
     public class UIControl {
         private boolean isEnabled; // Private field
         
         public void setEnabled(boolean enabled) {
             this.isEnabled = enabled;
         }
     }
     ```
   - Attempting to access `isEnabled` from outside the class will result in a compilation error.

2. **Protected Members**:
   - Protected members are accessible within the same package and by subclasses in different packages.
   - **Example**: A `protected` field in the `UIControl` class:
     ```java
     protected int width; // Accessible to subclasses and within the same package
     ```

## Upcasting and Downcasting
1. **Upcasting**: Casting a subclass object to a superclass type.
   - **Example**: Passing a `TextBox` object to a method expecting a `UIControl`:
     ```java
     public void show(UIControl control) {
         System.out.println(control);
     }

     TextBox textBox = new TextBox("Hello World");
     show(textBox); // Upcasting
     ```

2. **Downcasting**: Casting a superclass reference back to a subclass type.
   - **Example**:
     ```java
     UIControl control = new TextBox("Hello World");
     if (control instanceof TextBox) {
         TextBox textBox = (TextBox) control; // Downcasting
         System.out.println("Content: " + textBox.getContent());
     }
     ```

## Comparing Objects
1. **Overriding `equals()` and `hashCode()`**:
   - **Example**: In a `Point` class, implement equality based on coordinates:
     ```java
     public class Point {
         private int x, y;

         public Point(int x, int y) {
             this.x = x;
             this.y = y;
         }

         @Override
         public boolean equals(Object obj) {
             if (this == obj) return true;
             if (!(obj instanceof Point)) return false;
             Point other = (Point) obj;
             return this.x == other.x && this.y == other.y;
         }

         @Override
         public int hashCode() {
             return Objects.hash(x, y); // Generate hash based on coordinates
         }
     }
     ```

## Final and Abstract Classes
1. **Final Classes**: Declaring a class as `final` prevents it from being subclassed.
   - **Example**: A utility class:
     ```java
     public final class MathUtil {
         public static int add(int a, int b) {
             return a + b;
         }
     }
     ```

2. **Abstract Classes**: An abstract class cannot be instantiated and can contain abstract methods that must be implemented by subclasses.
   - **Example**:
     ```java
     public abstract class Shape {
         public abstract double area(); // Abstract method
     }
     ```

## Conclusion
Understanding and applying these object-oriented programming principles—encapsulation, inheritance, polymorphism, and proper usage of access modifiers—enhances code maintainability and reusability in Java. By refactoring procedural code into an object-oriented structure, developers can create more robust and manageable applications, demonstrating the true power of OOP.
```

This version provides detailed explanations and vivid examples, illustrating how each concept is applied in Java programming.
     }
     ```



This summary elaborates on the key concepts discussed, providing clear examples to illustrate the principles of object-oriented programming effectively.
