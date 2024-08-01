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

```
example
          // C program to demonstrate the use of file inclusion
          // directive #include.
      
          #include <stdio.h> // includng header file for Standard input/output functions
          #include <stdlib.h> // includng header file for Standard library functions
          
          int main()
          {
              // Using  standard input/output functions from stdio.h
              printf("Hello, Geek!\n");
          
              // Using standard library functions
              int num1 = 10, num2 = 5;
              int sum = num1 + num2;
          
              // displayng the result using printf from stdio.h
              printf("Sum: %d\n", sum);
              return 0;
          }
```
```
Output
    Hello, Geek!
    Sum: 15

```
### **User-defined Header Files**

When a program becomes very large, it is a good practice to divide it into smaller files and include them whenever needed. These types of files are user-defined header files.

```console
Syntax
  #include "filename"
```
The double quotes ( ” ” ) tell the compiler to search for the header file in the source file’s directory.
