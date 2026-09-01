# linker
The linker is a program responsible for finding the actual definitions of all functions declared in the program and connecting them to the placeholders created during compilation. The linker searches for function definitions in:
* **Standard Library Paths**: The standard library paths are pre-configured during the installation of the compiler.
* **Custom Libraries**: If you're using custom functions, you provide the .c or .o file, or specify the library path during linking.
* **Default Library Files**:The compiler/linker automatically links to libraries like libc for standard functions unless told otherwise.  

### How Does a Header File inclusion Provide Access to Library Functions?
* A header file contains function declarations (prototypes), macro definitions, and other definitions necessary to use a library's functions.
* It tells the compiler what functions exist, their names, return types, and parameters.
* Example: `stdio.h` is a header file that provides declarations for functions like `printf()` and `scanf()`.
* When you include a header file using the #include directive, the contents of the header file are copied into your program during the preprocessing phase.
* The function implementations themselves are not in the header file. They reside in the library files (e.g., .lib or .a files).
* When you compile the program, the linker links the compiled object code of your program to the compiled code of the library functions.



# Practical Example
File: functions.h
```
#ifndef FUNCTIONS_H
#define FUNCTIONS_H

void greet();  // Declaration

#endif
```
File: functions.c
```
#include <stdio.h>

void greet() {  // Definition
    printf("Hello from the greet function!\n");
}
```
File: main.c
```
#include "functions.h"

int main() {
    greet();  // Function call
    return 0;
}
```
```bash
# To compile and link:
gcc main.c functions.c -o program
```
Here:
* The compiler uses functions.h to check the greet function in main.c.
* The linker resolves the greet definition from functions.c.


### how a compiler find where the function defintion is, from a function declaration in header file
* consider we included a header file using #include ,that contains declaration of the function we used in our source file
* when we try to build the main source file
* preprocessor copy paste the entire content of header file to our main source file.
* during the compilation phase The compiler uses the function declaration to:
    * Verify that the function calls in the code match the declaration in terms of return type, argument types, and argument count.
    *  The declaration in a header file acts as a "promise" that the function exists somewhere, enabling the compiler to compile the code.
    * Generate an object file for the program but leaves placeholders for the function definitions (these are called undefined symbols). 
   
