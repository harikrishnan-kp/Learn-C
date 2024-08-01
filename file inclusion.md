# file inclusion
- This type of preprocessor directive tells the compiler to include a file in the source code program.
- The **#include** preprocessor directive is used to include the header files in the C program.

There are two types of files that can be included by the user in the program:
- Standard Header Files
- User-defined Header Files

### **Standard Header Files**

The standard header files contain definitions of pre-defined functions like printf(), scanf(), etc. These files must be included to work with these functions. Different functions are declared in different header files.
For example, standard I/O functions are in the ‘iostream’ file whereas functions that perform string operations are in the ‘string’ file. 

```console
Syntax
  #include <file_name>
```
where file_name is the name of the header file to be included. The ‘<‘ and ‘>’ brackets tell the compiler to look for the file in the standard directory.

### **User-defined Header Files**

When a program becomes very large, it is a good practice to divide it into smaller files and include them whenever needed. These types of files are user-defined header files.

```console
Syntax
  #include "filename"
```
The double quotes ( ” ” ) tell the compiler to search for the header file in the source file’s directory.
