### Key Points Summary on Clean Code and Methods

- **Importance of Clean Code**: Keeping code clean and organized is crucial, just like maintaining a tidy house. Clean code is easier to read, understand, and maintain.

- **Breaking Down Code**: As programs grow in size, it's essential to break code into smaller, manageable methods. This enhances readability and reusability.

- **Creating Methods**: 
  - Example of a simple method:
    ```java
    public static void greet(String name) {
        System.out.println("Hello " + name);
    }
    ```
  - Call the method in the main function:
    ```java
    greet("Mosh"); // Outputs: Hello Mosh
    ```

- **Method Parameters**: Methods can take multiple parameters separated by commas. For example:
  ```java
  public static void greetUser(String firstName, String lastName) {
      System.out.println("Hello " + firstName + " " + lastName);
  }
  ```
- **Returning Values**: Methods can also return values. Change the return type and use the return statement:

```java
public static String greetUser(String firstName, String lastName) {
    return "Hello " + firstName + " " + lastName;
}
```

- **Refactoring**: Refactoring involves restructuring code without changing its behavior. Extracting repeated logic into methods improves clarity and maintainability.

- **Common Compile-Time Errors**:
  - Forgetting to specify a variable's type.
  - Missing semicolons.
  - Incorrectly using an operator (e.g., using `=` instead of `==`).

- **Debugging**:
  - Use breakpoints to pause execution and inspect variable values.
  - Step through code to identify bugs.
  - Utilize the call stack to trace method calls.

- **Loop Types**:
  - **For Loop**: Used when the number of iterations is known.
  - **While Loop**: Used when the number of iterations is uncertain.
  - **Do While Loop**: Executes at least once, regardless of the condition.
  - **For Each Loop**: Simplifies iteration over collections or arrays.
