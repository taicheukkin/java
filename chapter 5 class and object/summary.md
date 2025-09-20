
# Summary of class and object

## Part 1: Static Fields and Methods
1. **Static Fields**: In Java, static fields are shared across all instances of a class. For example, consider a class `Employee` with a static field `numberOfEmployees`. Every time a new `Employee` object is created, the `numberOfEmployees` is incremented. This allows you to track the total number of employees without requiring an instance to access it.

   ```java
   class Employee {
       static int numberOfEmployees = 0;

       Employee() {
           numberOfEmployees++;
       }
   }
   ```

2. **Use Cases**: Static members are ideal for concepts that should be consistent across all instances. For instance, if you have a `School` class, a static field `schoolName` could represent the name of the school that applies to all students.

3. **Static Methods**: Static methods can only access static fields or other static methods in the same class. For example, if you have a static method `printNumberOfEmployees()` in the `Employee` class, it can print the `numberOfEmployees` without needing to create an `Employee` instance.

   ```java
   class Employee {
       static int numberOfEmployees = 0;

       static void printNumberOfEmployees() {
           System.out.println("Total Employees: " + numberOfEmployees);
       }
   }
   ```

## Part 2: Creating a New Class
1. **Class Creation**: Using IntelliJ, you create a new class called `TextBox`. This class might have a public access modifier, a string field for storing text, and methods for setting and clearing the text.

   ```java
   class TextBox {
       public String text;

       public void setText(String text) {
           this.text = text;
       }

       public void clear() {
           this.text = "";
       }
   }
   ```

2. **Using `this` Keyword**: The `this` keyword differentiates instance variables from parameters. For instance, in the `setText` method, `this.text` refers to the instance variable while `text` refers to the parameter.

## Part 3: Creating and Using Objects
1. **Instantiating the Class**: You create instances of the `TextBox` class like this:

   ```java
   TextBox box1 = new TextBox();
   ```

2. **Method Calls**: You can set and retrieve text from your text box like this:

   ```java
   box1.setText("Hello World");
   System.out.println(box1.text); // Outputs: Hello World
   ```

3. **Handling Null Values**: Always initialize string fields to avoid null pointer exceptions. For example, initializing `text` to an empty string prevents errors when trying to access it.

## Part 4: Memory Allocation in Java
1. **Memory Areas**: Java manages memory in two areas:
   - **Heap**: Stores objects. For example, when you create a `TextBox` object, it resides in the heap.
   - **Stack**: Stores short-lived variables, like primitive types (e.g., integers) and references to objects.

2. **Creating Objects**: When you create a `TextBox` object, Java allocates memory in the heap and stores its address in the stack.

   ```java
   TextBox box2 = new TextBox(); // box2 holds the reference to the heap object
   ```

3. **Reference Types vs. Primitive Types**: Consider this example:

   ```java
   int age = 30; // Primitive type stored directly in stack
   TextBox box3 = new TextBox(); // Reference type stored in stack, points to heap object
   ```

4. **Variable References**: If `box1` and `box2` reference the same `TextBox` object, modifying it through one reference affects the other:

   ```java
   box2.setText("Goodbye");
   System.out.println(box1.text); // Outputs: Goodbye
   ```

5. **Memory Deallocation**: Java's garbage collector automatically handles memory. If an object has no references (e.g., after exiting a method), it becomes eligible for garbage collection.

6. **Garbage Collection**: When the Java runtime detects an object is no longer referenced, it automatically removes it from the heap, freeing up memory.

Here's a comprehensive summary in Markdown format, incorporating vivid examples and covering the principles of object-oriented programming, encapsulation, and abstraction:


# Summary of Object-Oriented Programming Concepts

## Part 1: The Benefits of Object-Oriented Programming
1. **Introduction to OOP**: The course emphasizes the benefits of object-oriented programming (OOP) over procedural programming. OOP enhances code organization and reusability.

2. **Example Program**: The initial example involves calculating employee wages using a procedural approach:
   - **Variables**: Declare variables such as `baseSalary`, `extraHours`, and `hourlyRate`.
   - **Wage Calculation**: Implement a method `calculateWage` that computes wages using these variables.

   ```java
   public static int calculateWage(int baseSalary, int extraHours, int hourlyRate) {
       return baseSalary + (extraHours * hourlyRate);
   }
   ```

3. **Issues with Procedural Programming**:
   - **Code Bloat**: As functionality expands, the main method becomes bloated with numerous lines, making it hard to manage.
   - **Lack of Reusability**: Functions are scattered, leading to duplication of code when used in multiple places.

## Part 2: Encapsulation
1. **Encapsulation Principle**: Encapsulation bundles data and methods that operate on that data within a single unit, or class. For instance, create an `Employee` class that contains fields for `baseSalary`, `hourlyRate`, and `extraHours`.

   ```java
   class Employee {
       private int baseSalary;
       private int hourlyRate;
       private int extraHours;

       public void setBaseSalary(int baseSalary) {
           if (baseSalary <= 0) {
               throw new IllegalArgumentException("Salary must be positive");
           }
           this.baseSalary = baseSalary;
       }

       public int calculateWage() {
           return baseSalary + (extraHours * hourlyRate);
       }
   }
   ```

2. **Data Validation**: Encapsulating data within the class allows for validation. For example, if an invalid salary is entered, an exception will be thrown, preventing the employee object from entering an invalid state.

3. **Cleaner Code**: By encapsulating the data, the main class remains clean and manageable. You can set values directly using methods without exposing the internal state of the class.

   ```java
   Employee employee = new Employee();
   employee.setBaseSalary(50000);
   employee.setHourlyRate(20);
   int wage = employee.calculateWage();
   System.out.println("Employee Wage: " + wage);
   ```

## Part 3: Abstraction
1. **Abstraction Principle**: Abstraction simplifies complex reality by hiding unnecessary details and showing only the essential features. For example, consider a TV remote control:
   - **User Interaction**: You interact with buttons to change channels without needing to understand the underlying electronics.

2. **Implementation in Code**: In the `Employee` class, fields are made private to hide implementation details. Instead of allowing direct access to fields, methods like setters and getters are provided.

   ```java
   private void setHourlyRate(int hourlyRate) {
       if (hourlyRate <= 0) {
           throw new IllegalArgumentException("Hourly rate must be positive");
       }
       this.hourlyRate = hourlyRate;
   }

   private int getHourlyRate() {
       return hourlyRate;
   }
   ```

3. **Encapsulation and Abstraction Together**: By combining encapsulation and abstraction, you create a robust design. Users of the `Employee` class don't need to know how salaries are calculated or stored; they just use methods to interact with the data.

4. **Example of Abstraction**: If the internal representation of an employee's wage changes (e.g., switching from integers to an array), only the `Employee` class needs updating, not every class that uses it.



# Summary of Object-Oriented Programming Concepts2

## Part 1: Coupling
1. **Understanding Coupling**: Coupling refers to how much a class depends on or is connected to another class. It’s important to manage coupling to avoid tightly interlinked classes that complicate changes.

   - **Example**: If Class A uses Class B extensively, any modification in Class B may require changes in Class A and possibly other classes that depend on it. This can lead to significant maintenance challenges in larger applications.

   ```java
   class A {
       private B b = new B();

       public void doSomething() {
           b.performAction();
       }
   }
   ```

   - **Impact of Coupling**: In a complex application with thousands of classes, changing one class can break many others, making the system fragile.

2. **Reducing Coupling**: Aim to reduce coupling to minimize the impact of changes. For example, use interfaces or abstract classes to define contracts that can be implemented by multiple classes.

   ```java
   interface Action {
       void performAction();
   }

   class B implements Action {
       public void performAction() {
           // Implementation here
       }
   }

   class A {
       private Action action;

       public A(Action action) {
           this.action = action;
       }

       public void doSomething() {
           action.performAction();
       }
   }
   ```

# part2 Encapsulation and Constructor Usage in Java


## Identifying Issues
1. **Initial State Problem**: If methods to set the employee's salary are not called, the `Employee` object can start in an invalid state, with fields like `baseSalary` defaulting to `0`.
   
   - **Example**: If we forget to call the methods that initialize the salary, running the program may yield:
   ```java
   System.out.println(employee.baseSalary); // Outputs: 0
   ```

2. **Public Fields**: Making the `baseSalary` public to read its value before calculations exposes the internal state and may lead to unintended modifications.

## Improving Design
1. **Encapsulation**: To prevent direct access to fields, we should make them private and provide setter methods to enforce rules around their values.

   ```java
   private int baseSalary;

   public void setBaseSalary(int salary) {
       if (salary < 0) {
           throw new IllegalArgumentException("Salary must be positive");
       }
       this.baseSalary = salary;
   }
   ```

2. **Constructor Usage**: Instead of relying on setters post-creation, we can ensure the object is always in a valid state by initializing fields through a constructor.

   ```java
   public Employee(int baseSalary) {
       setBaseSalary(baseSalary); // Use setter for validation
   }
   ```

3. **Constructor Overloading**: If we want flexibility in object creation, we can overload constructors to allow for different initialization scenarios.

   ```java
   public Employee(int baseSalary, int hourlyRate) {
       this(baseSalary); // Calls the first constructor
       this.hourlyRate = hourlyRate;
   }
   ```

## Benefits of the Improved Design
1. **Cleaner Interface**: By hiding implementation details and reducing the number of public methods, the interface of the `Employee` class becomes simpler and easier to use.

   - **Example**: Now the `Employee` class might only expose necessary methods:
   ```java
   public int calculateWage() {
       return baseSalary; // Simplified calculation
   }
   ```

2. **Preventing Invalid States**: Using constructors and setters ensures that an `Employee` instance cannot exist in an invalid state, reducing potential bugs.

3. **Abstraction in Action**: By hiding unnecessary details from users and exposing only what they need to interact with, we adhere to the principle of abstraction in object-oriented programming.



## Part 3: Method Overloading
1. **Overloading Methods**: Method overloading allows you to create multiple methods with the same name but different parameters. This provides flexibility in how methods are called.

   ```java
   class Employee {
       public int calculateWage(int extraHours) {
           // Logic for calculating wage with extra hours
       }

       public int calculateWage() {
           return baseSalary; // No extra hours
       }
   }
   ```

2. **Using Overloaded Methods**: You can call overloaded methods based on the parameters provided, making your code cleaner and more intuitive.

Here's a Markdown summary that captures the essence of method overloading and constructor overloading in object-oriented programming, along with examples for clarity:

```markdown
# Summary of Method and Constructor Overloading in Java

## Method Overloading
1. **Concept**: Method overloading allows you to define multiple methods with the same name but different parameters. This enables a class to perform similar operations with different inputs.

   - **Example**: In an `Employee` class, you can have a `calculateWage` method that takes extra hours as a parameter:
   ```java
   public int calculateWage(int extraHours) {
       return baseSalary + (extraHours * hourlyRate);
   }
   ```

   - **Overloaded Method**: You can also create an overloaded version that calculates wages with no extra hours:
   ```java
   public int calculateWage() {
       return baseSalary; // Returns only the base salary
   }
   ```

## part 4 Constructor Overloading
1. **Definition**: Constructors can also be overloaded like methods. A constructor is a special method that initializes an object when it's created.

   - **Example**: In the `Employee` class, you can have a constructor that takes base salary and hourly rate:
   ```java
   public Employee(int baseSalary, int hourlyRate) {
       this.baseSalary = baseSalary;
       this.hourlyRate = hourlyRate;
   }
   ```

   - **Overloaded Constructor**: You can create another constructor that initializes an employee with only a base salary, assuming no extra hours:
   ```java
   public Employee(int baseSalary) {
       this(baseSalary, 0); // Calls the first constructor with 0 as hourly rate
   }
   ```

2. **Using `this` Keyword**: Within a constructor, you can use `this` to reference the current object, allowing you to call another constructor:
   ```java
   public Employee(int baseSalary) {
       this(baseSalary, 0); // Calls the main constructor
   }
   ```

## Practical Implementation
1. **Creating Instances**: You can create instances of the `Employee` class using either constructor:
   ```java
   Employee emp1 = new Employee(50000, 20); // With both parameters
   Employee emp2 = new Employee(50000); // Only base salary
   ```

2. **Benefits of Overloading**:
   - **Flexibility**: Allows methods and constructors to cater to different use cases without requiring unique names.
   - **Cleaner Code**: Reduces the complexity of the API, making it easier for users to work with the class.





## Part 5: Static Fields and Methods
1. **Static Members**: Static fields and methods belong to the class rather than any instance. They are shared among all instances of the class.

   ```java
   class Employee {
       static int numberOfEmployees = 0;

       public Employee() {
           numberOfEmployees++;
       }
   }
   ```

2. **Accessing Static Members**: You can access static members directly through the class name without needing to create an instance.

   ```java
   System.out.println(Employee.numberOfEmployees);
   ```

3. **Static Methods**: Static methods can only access other static methods or fields within the same class. They cannot access instance methods without creating an object.

   ```java
   class Employee {
       public static void printEmployeeCount() {
           System.out.println("Total Employees: " + numberOfEmployees);
       }
   }
   ```

