arkdown

複製
# Summary of "Ultimate Java Part 1" by Mosh

## 1.1 Fundamentals

### Downloading and Installing Java Development Kit (JDK)
The tutorial begins with instructions on downloading and installing the **Java Development Kit (JDK)**, essential for building Java applications. The JDK includes a compiler, reusable code libraries, and the **Java Runtime Environment (JRE)**. The recommended source is Oracle’s official website, where users can select the appropriate JDK version for their operating system (Linux, Mac OS, Windows). The installation process is straightforward, involving accepting the license agreement and running the installation wizard.

### Choosing a Code Editor
Next, the tutorial discusses selecting a code editor for Java development. Popular editors include **NetBeans**, **Eclipse**, and **IntelliJ IDEA**. The course uses **IntelliJ IDEA Community Edition**, which is free and sufficient for learning Java. The installation involves downloading the DMG file (for Mac) and moving it to the Applications folder.

### Anatomy of a Java Program
The smallest building block in Java is a **function** (also called a **method** when inside a class). Functions perform specific tasks, similar to buttons on a TV remote. Functions can return values or be void (return nothing). The syntax involves specifying the return type, function name, parameters in parentheses, and the function body enclosed in curly braces. Java conventions place the opening brace on the same line as the function declaration.

Every Java program must have a **main function**, which serves as the entry point. Functions belong to **classes**, which organize related functions (methods). Classes are containers for methods, similar to how supermarkets organize products into sections. Every Java program requires at least one class containing the main method, often named **Main**. Java uses access modifiers like **public** and **private** to control visibility of classes and methods. The **public** modifier is commonly used to make classes and methods accessible from other parts of the program.

### Naming Conventions
Java uses **PascalCase** for class names (each word capitalized) and **camelCase** for method names (first word lowercase, subsequent words capitalized). This explains why the class **Main** starts with a capital letter.

### Creating and Running a Java Project in IntelliJ IDEA
The tutorial guides through creating a new Java project in IntelliJ IDEA:
- Select Java and ensure the JDK is set.
- Choose to create a project from a template, specifically a command-line application.
- Name the project (e.g., **hello world**).
- Set the base package, typically a reversed domain name (e.g., **com.codewithmosh**). Packages group related classes and help organize large projects. The project structure includes a source folder containing the base package and the **Main.java** file. Java files must have the **.java** extension.

### Understanding the Main Class and Method
The **Main.java** file starts with a package declaration, followed by the class definition and the main method. The main method is `public static void main(String[] args)` and accepts a parameter array of strings. Comments, indicated by `//`, explain the code but do not execute.

### Writing the First Java Program
The tutorial demonstrates printing "Hello World" to the terminal using java:

System.out.println("Hello World");

- **System** is a class in the `java.lang` package.
- **out** is a static field of type **PrintStream**.
- **println** is a method that prints text followed by a new line. Textual data in Java is represented as strings, enclosed in **double quotes**.

### Running the Program
The program can be run using the **IntelliJ toolbar** or keyboard shortcut (**Control + R** on Mac). The output appears in the terminal window within IntelliJ.

### How Java Code is Executed
Java execution involves two steps: **compilation** and **execution**.

- **Compilation:** The Java compiler (`javac`) converts `.java` source files into `.class` files containing Java bytecode. This bytecode is platform-independent.
- **Execution:** The Java Virtual Machine (JVM) translates bytecode into native machine code for the operating system. This portability allows Java programs to run on any OS with a JVM.

The tutorial shows how to compile and run Java programs manually using the terminal:
- Compile with `javac Main.java`.
- Run with `java com.codewithmosh.Main` (using the full package and class name).

### Interesting Facts About Java
- Developed by **James Gosling** in **1995** at **Sun Microsystems**, later acquired by **Oracle**.
- Originally named **Oak**, then **Green**, and finally **Java**, inspired by Java coffee.
- Java has four editions:
  - **Standard Edition (SE):** Core platform used in this course.
  - **Enterprise Edition (EE):** For large-scale distributed systems.
  - **Micro Edition (ME):** For mobile devices.
  - **JavaCard:** For smart cards.
- Java SE 12 was the latest version as of **March 2019**.
- Java has about **9 million developers** worldwide.
- Java runs on approximately **3 billion mobile phones**, **120 million TVs**, and **Blu-ray players**.
- The average salary for a Java developer in the US is over **$100,000** per year.

### Course Structure Overview
This course is the first part of a **four-part Java series**, each lasting **3-4 hours**:
- **Part 1 (Current):** Fundamentals of Java programming.
- **Part 2:** Java type system including numbers, strings, booleans, and arrays. The first project is a **mortgage calculator**.
- **Part 3:** Control flow statements like conditionals and loops, plus data validation.
- **Part 4:** Clean coding practices for maintainable and expressive code.
- **Part 5:** Error handling, debugging, and packaging Java applications for deployment.

Future parts of the series will cover:
- **Object-oriented programming (OOP)**, essential for Java applications.
- Core Java **APIs**, exploring useful standard library classes.
- Advanced Java features such as **streams**, **threads**, and **database programming**.

The course aims to provide a **solid foundation** for mastering Java, a widely used programming language behind millions of applications and websites.
