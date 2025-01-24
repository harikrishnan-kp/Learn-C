
# Compiling a C Program: Behind the Scenes

The compilation is the process of converting the source code of the C language into machine specific assembly code. 

note:
* output will be a .s file
* compiler also do optmization in code

The compiler uses the function declaration to:
    * Verify that the function calls in the code match the declaration in terms of return type, argument types, and argument count.
    *  The declaration in a header file acts as a "promise" that the function exists somewhere, enabling the compiler to compile the code.
    * Generate an object file for the program but leaves placeholders for the function definitions (these are called undefined symbols). 