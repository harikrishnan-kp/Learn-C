# Header file
* header files are the files with `.h` extension that contains function declarations (prototypes), macro definitions, constants,  variables, type definitions and other definitions necessary.
* it enhances the organization, modularity, and reusability of your code.

## Key Contents of a Header File
* `Function Prototypes`: Declare functions to be used in multiple source files.
```
int add(int a, int b);
```
* `Macros`: Define constants or inline code for reuse.
```
#define PI 3.14159
```
* `Type Definitions`: Define new data types.(user defined data type)
```
typedef struct {
    int x;
    int y;
} Point;
```
* `Global Variable Declarations`: Declare global variables for external linkage.
```
extern int global_var;
```
* `Include Guards or #pragma once`: Prevent multiple inclusions of the same header file.
```
#ifndef MY_HEADER_H
#define MY_HEADER_H
// Header file content
#endif
```
## Importance of Header Files in C Programming
* **Code Organization and Reusability**: Header files allow you to separate declarations from implementation, making your code modular and reusable.You can use the same header file in multiple .c files, avoiding redundant declarations.
* **Improves Readability**: Function prototypes and constants in a header file provide a clear overview of a module's interface, making it easier to understand and maintain.
* **Encapsulation**: Implementation details are hidden in the .c file, while the header file exposes only the necessary parts (e.g., function prototypes) to other parts of the program.
* **Reduces Errors**: Function prototypes in the header file ensure that the function signatures match between their declaration and implementation. This helps catch errors at compile time.
* **Supports Modular Programming**: Header files enable teams to develop different parts of a program independently by providing a clear interface for communication between modules.
* **Provides Standard Libraries**: Standard libraries like <stdio.h>, <stdlib.h>, and <math.h> are header files that declare commonly used functions (e.g., printf, malloc, sqrt) and constants.
* **Facilitates Code Sharing Across Projects**: If you write reusable modules, you can simply share the header files to let others use your functions without exposing the implementation.

## Classification of header files
header files are classified into two
### **Standard Header Files**
The standard header files contain declarations of pre-defined functions like printf(), scanf(), etc. These files must be included to work with these functions. Different functions are declared in different header files.
For example, standard I/O functions are in the ‘iostream’ file whereas functions that perform string operations are in the ‘string’ file. 
```
eg: stdio.h, math.h
```
### **User-defined Header Files**
header files written by user for reducing complexity and modularity

## FAQ
* what are standard header files and user defined header files
* is it mandatory for header files to have same name as its respective source file
    * No, it is not mandatory to use the same name for a .c file and its corresponding .h file, but it is a common and recommended practice for better organization,readability and Standardization in your codebase.
    * You are free to name your source files and header files differently if needed, as long as:
        * The #include directive in your .c file correctly references the appropriate .h file.
        * There are no name conflicts or ambiguities.
* if we use different names for .c and .h file, does that cause any problem for using the .h in another .c file


