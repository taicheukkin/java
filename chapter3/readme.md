### Key Points Summary

- **Comparison Operators**: Used to compare primitive values.
  - Example: 
    ```java
    int x = 5;
    int y = 10;
    boolean isEqual = (x == y); // false
    ```

- **Boolean Expressions**: Expressions that produce a boolean value (true or false).
  - Example:
    ```java
    boolean isNotEqual = (x != y); // true
    ```

- **Logical Operators**: Combine multiple boolean expressions.
  - Example:
    ```java
    boolean isWarm = (temperature > 20 && temperature < 30); // true if temperature is between 20 and 30
    ```

- **If Statements**: Allow decisions based on conditions.
  - Example:
    ```java
    if (temperature > 30) {
        System.out.println("It's a hot day.");
    } else if (temperature > 20) {
        System.out.println("It's a nice day.");
    } else {
        System.out.println("It's a cold day.");
    }
    ```

- **Ternary Operator**: A shorthand for if-else statements.
  - Example:
    ```java
    String className = (income > 100000) ? "First Class" : "Economy";
    ```

- **Switch Statements**: Execute different code segments based on the value of an expression.
  - Example:
    ```java
    switch (role) {
        case "admin":
            System.out.println("You're an admin.");
            break;
        case "moderator":
            System.out.println("You're a moderator.");
            break;
        default:
            System.out.println("You're a guest.");
            break;
    }
    ```

- **Loops**: Allow repeating code multiple times.
  - **For Loop**:
    ```java
    for (int i = 0; i < 5; i++) {
        System.out.println("Hello World " + i);
    }
    ```
  
  - **While Loop**:
    ```java
    int i = 0;
    while (i < 5) {
        System.out.println("Hello World " + i);
        i++;
    }
    ```

  - **Do While Loop**: Executes at least once.
    ```java
    int i = 0;
    do {
        System.out.println("Hello World " + i);
        i++;
    } while (i < 5);
    ```

- **Break Statement**: Exits the loop immediately.
  - Example:
    ```java
    if (input.equals("quit")) {
        break; // exits the loop
    }
    ```

- **Continue Statement**: Skips the current iteration and continues with the next iteration.
  - Example:
    ```java
    if (input.equals("pass")) {
        continue; // skips the rest of the loop for this iteration
    }
    ```

- **For Each Loop**: Iterates over elements in an array or collection.
  - Example:
    ```java
    String[] fruits = {"Apple", "Mango", "Orange"};
    for (String fruit : fruits) {
        System.out.println(fruit); // prints each fruit
    }
    ```
