# C Preprocessors
Preprocessors are programs that process the source code before compilation. Several steps are involved between writing a program and executing a program in C. 

<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Preprocessor-In-C.png" height="300" width="600"> 


You can see the intermediate steps in the above diagram. The source code written by programmers is first stored in a file, let the name be “****program.c****“. This file is then processed by preprocessors and an expanded source code file is generated named “program.i”. This expanded file is compiled by the compiler and an object code file is generated named “program.obj”. Finally, the linker links this object code file to the object code of the library functions to generate the executable file “program.exe”.

## Preprocessor Directives in C

Preprocessor programs provide preprocessor directives that tell the compiler to preprocess the source code before compiling. All of these preprocessor directives begin with a ‘#’ (hash) symbol. The ‘#’ symbol indicates that whatever statement starts with a ‘#’ will go to the preprocessor program to get executed. We can place these preprocessor directives anywhere in our program.

Examples of some preprocessor directives are: __#include__, __#define__, __#ifndef,__ etc.

> ****Note**** Remember that the ****#**** symbol only provides a path to the preprocessor, and a command such as include is processed by the preprocessor program. For example, #include will include the code or content of the specified file in your program.


### **List of preprocessor directives in C**

The following table lists all the preprocessor directives in C:

**Preprocessor Directives :  Description**

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


# **new content**
A Preprocessor is a system software (a computer program that is designed to run on computer’s hardware and application programs). It performs preprocessing of the High Level Language(HLL). Preprocessing is the first step of the language processing system. Language processing system translates the high level language to machine level language or absolute machine code(i.e. to the form that can be understood by machine).

The preprocessor doesn’t know about the scope rules of C. Preprocessor directives like #define come into effect as soon as they are seen and remain in effect until the end of the file that contains them; the program’s block structure is irrelevant. 

<img src="https://media.geeksforgeeks.org/wp-content/uploads/Preprocessor.png" height="300" width="200">

A Preprocessor mainly performs three tasks on the HLL code :

- **Removing comments** : It removes all the comments. A comment is written only for the humans to understand the code. So, it is obvious that they are of no use to a machine. So, preprocessor removes all of them as they are not required in the execution and won’t be executed as well. This file is saved with a ‘.i’ extension (prog.i) which will be input to the compiler. 
- **File inclusion** : Including all the files from library that our program needs. In HLL we write #include which is a directive for the preprocessor that tells it to include the contents of the library file specified. For example, #include will tell the preprocessor to include all the contents in the library file stdio.h.
This can also be written using double quotes – #include “stdio.h”
Note: If the filename is enclosed within angle brackets, the file is searched for in the standard compiler include paths. If the filename is enclosed within double quotes, the search path is expanded to include the current source directory.
- **Macro expansion** : Macros can be called as small functions that are not as overhead to process. If we have to write a function (having a small definition) that needs to be called recursively (again and again), then we should prefer a macro over a function.So, defining these macros is done by preprocessor. 
