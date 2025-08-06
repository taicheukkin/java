ToString() for multidimensional arrays.markdown

### Using Variables in Java
In this tutorial, we discuss variables in Java, which are used to temporarily store data in a computer's memory. For example, to store someone's age, we declare a variable like this

int age = 30;
- The int type allows us to store whole numbers. We initialize a variable by assigning it a value, and we must do this before reading the variable. You can print the value of the variable using:

System.out.println(age);
- You can also change the variable's value after initialization. It’s best to declare one variable per line to keep your code readable. You can copy a variable's value to another variable as follows:
```
int myAge = age;
```

### Basic Types in Java
Java has two categories of types: **primitive types** for storing simple values and **reference types** for storing complex objects. The primitive types include:
```
byte: 1 byte, values from -128 to 127
short: 2 bytes, values from -32,768 to 32,767
int: 4 bytes, values from -2,147,483,648 to 2,147,483,647
long: 8 bytes, larger values
float: 4 bytes, decimal values
double: 8 bytes, higher precision decimal values
char: 2 bytes, single characters
boolean: true or false values
```


### Differences Between Reference Types and Primitive Types

Primitive types are copied by their value, while reference types are copied by their reference. For example:
java
```int x = 1;
int y = x       // y is independent of x
   x = 2;
```
In contrast, when using reference types, both variables can refer to the same object.
```
   myobj= new myobj()
   myobj=myobj1
   myobj1=2;
```

### Using Arrays in Java
Arrays store lists of items, like numbers or messages. To create an array, you specify its size:

java
```
int[] numbers = new int[5];
```
You can access individual items using their index. If you try to access an **invalid index**, an exception will be raised. Arrays have a fixed size, and to add or remove items, you should use collection classes.

Multidimensional Arrays
You can create **multidimensional arrays**, such as a 2D array for a matrix:

java
```
int[][] matrix = new int[2][3];                                                     
```
To print the contents of an array, you can use **Arrays.toString()** or **Arrays.deep**

### Key Points Summary

- **Variables in Java**: Variables are used to temporarily store data. They must be initialized before use. 
  - Example: `int age = 30;`

- **Constants**: Use the `final` keyword to declare constants that should not change. By convention, constants are named in all uppercase letters. 
  - Example: `final double PI = 3.14;`

- **Arithmetic Expressions**: Java supports arithmetic operations like addition, subtraction, multiplication, division, and modulus. 
  - Example: `int result = 10 + 3; // result is 13`

- **Type Casting**: 
  - **Implicit Casting**: Automatic conversion occurs when converting a smaller type to a larger type without data loss.
    - Example: `int x = 1; double y = x; // x is automatically converted to double`
  - **Explicit Casting**: Required when converting a larger type to a smaller type.
    - Example: `double a = 9.78; int b = (int) a; // b is 9`

- **Increment and Decrement Operators**: 
  - `x++` increases the value of `x` by 1.
    - Example: 
      ```java
      int x = 1;
      x++; // x is now 2
      ```
  - Use `x += 2` to increment `x` by 2.
    - Example: 
      ```java
      x += 2; // x is now 4
      ```

- **Operator Precedence**: Multiplication and division have higher precedence than addition and subtraction. Use parentheses to change the order of operations.
  - Example: `int result = 10 + 3 * 2; // result is 16`

- **Scanner Class**: Used to read user input from the terminal. 
  - Example: 
    ```java
    Scanner scanner = new Scanner(System.in);
    int input = scanner.nextInt();
    ```

- **Reading Input**: Methods like `nextInt()`, `next()`, and `nextLine()` are used to read different types of input.
  - Example: 
    ```java
    String name = scanner.nextLine(); // reads a whole line
    ```

- **Trimming Input**: Use the `trim()` method to remove leading and trailing whitespace from strings.
  - Example: 
    ```java
    String trimmedName = name.trim();
    ```

- **Method Chaining**: You can chain methods together, such as calling `trim()` on the result of `nextLine()` to clean up user input.
  - Example: 
    ```java
    String cleanInput = scanner.nextLine().trim();
    ```
