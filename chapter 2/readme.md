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
int y = x; // y is independent of x
```
In contrast, when using reference types, both variables can refer to the same object.

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
