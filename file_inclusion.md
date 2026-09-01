# file inclusion
- This type of preprocessor directive are used to include a file in the source code, Usually header files
- `#include` is the preprocessor directive using for this operation.

```bash
Syntax
  #include <file_name>
```
- if we include a header file in a source file using #include, preprocessor will copy the entire content of header file to that source file 

## Example:
 consider the files main.c fun.c and fun.h 

File: fun.h
```
#ifndef FUNCTIONS_H
#define FUNCTIONS_H

int add(int a,int b);

#endif
```
File: fun.c
```
int add(int a, int b) {
  sum = a+b;
  return sum;
}
```
File: main.c
```
#include "fun.h"

int main() {
    add();  // Function call
    return 0;
}
```
After preprocessing main.c become
```
#ifndef FUNCTIONS_H
#define FUNCTIONS_H

int add(int a,int b);

#endif

int main() {
    greet();  // Function call
    return 0;
}
```
## note
When including a header file in the build process using the `#include` preprocessor directive, the toolchain needs to determine the file's location. This can be resolved using the following techniques:

* Using Double Quotes (`#include "file.h"`)
  * If the header file name is enclosed in double quotes, the toolchain searches for the file in the same directory as the input source file.
  * You can also specify a relative path to include files located in other directories.
* Using Angle Brackets (`#include <file.h>`)
  * If the file name is enclosed in angle brackets, the toolchain searches for the file in the standard compiler include paths.
* Specifying Include Paths Explicitly
  - You can explicitly tell the compiler where to find the header file by using the -I option followed by the directory name during build process.
    ```console
    -I <directory name>
    ```
These techniques ensure the build toolchain can locate the required header files efficiently.

## Example
C program to demonstrate the use of file inclusion

```console
  #include <stdio.h>  // Standard header file for input/output functions
  #include <stdlib.h> // header file for Standard library functions
  #include "user.h"   // user defined function (not used in code)

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

## FAQ
* Is it possible to include a `.c` file using #include directive?
  * yes. preprocessor will copy paste the entire content in it, However, it is not recommended and goes against best practices in software development