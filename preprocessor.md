# C Preprocessors
Preprocessors are programs that process the source file before compilation. Several steps are involved between writing a program and executing a program in C. 

<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Preprocessor-In-C.png" height="300" width="600"> 


You can see the intermediate steps in the above diagram. The source code written by programmers is first stored in a file, let the name be “****program.c****“. This file is then processed by preprocessors and an expanded source code file is generated named “program.i”. This expanded file is compiled by the compiler and an object code file is generated named “program.obj”. Finally, the linker links this object code file to the object code of the library functions to generate the executable file “program.exe”.

## Preprocessor Directives in C

Preprocessor directives are the special instructions that tell the build toolchain to preprocess the source code before compiling. All of these preprocessor directives begin with a ‘#’ (hash) symbol. The ‘#’ symbol indicates that whatever statement starts with a ‘#’ will go to the preprocessor program to get executed. We can place these preprocessor directives anywhere in our program.

Examples of some preprocessor directives are: __#include__, __#define__, __#ifndef,__ etc.

```console
Note
Remember that the # symbol only provides a path to the preprocessor, and a command such as include is processed by the preprocessor program.For example, #include will include the code or content of the specified file in your program.
```

### **List of preprocessor directives in C**

The following table lists all the preprocessor directives in C:

**Preprocessor Directives and Description**

* **#define**         : Used to define a macro

* **#undef**          : Used to undefine a macro

* **#include**        : Used to include a file in the source code program

* **#ifdef**          : Used to include a section of code if a certain macro is defined by #define

* **#ifndef**         : Used to include a section of code if a certain macro is not defined by #define

* **#if**             : Check for the specified condition

* **#else**           : Alternate code that executes when #if fails

* **#endif**          : Used to mark the end of #if, #ifdef, and #ifndef|  |

## **Types of C Preprocessors**
- There are 4 Main Types of Preprocessor Directives:  
  - [Macros](https://github.com/harikrishnan-kp/Learn-C/blob/main/macros.md)
  - [File Inclusion](https://github.com/harikrishnan-kp/Learn-C/blob/main/file%20inclusion.md)
  - [Conditional Compilation](https://www.geeksforgeeks.org/cc-preprocessors/?ref=lbp)
  - [Other directives](https://www.geeksforgeeks.org/cc-preprocessors/?ref=lbp)

