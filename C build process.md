# Building a C program
As C is a mid-level language, it need to convert into low level binary code so that the program can be run on our machine. **Build** is the process of converting high level language to executable binary file. this process required a set of tools commonly named as build **tool chain**. eg : **GCC**, **MINGW** 

a typical tool chain includes
* Preprocessor
* Compiler
* Assembler
* Linker

## Build and run a simple C program?

* Requirements :
    * code editor : helps us write C code. eg- nano,vim,cat or any text editor
    * build tool chain : for converting C source code to executable binary code.eg- GCC (GNU Compiler collection)
    * here we are going to use nano and gcc

* Step 1: Creating a C Source File

create a C program using an editor and save the file as filename.c

```console
 $ nano filename.c
```
write a simple hello world printing program in it and save it.
* Step 2: build the file using GCC tool chain

use the following command in the terminal for building our source file.

```console
$ gcc filename.c
```
if there is no errors in our program you will get a executable binary file named **a.out** as output 

* step 3: enable executable permission to the file and run it

```console
$ ./a.out
```
The program will be executed and the output will be shown in the terminal.

### note
* We can pass many instructions to the GCC compiler depends upon our needs:
* The option **-Wall** enables all compiler’s warning messages. This option is recommended to generate better code. 
* The option **-o** is used to specify the output file name. If we do not use this option, then an output file with the name a.out is generated.

for example

Give a specific name to executable file

```console
 $ gcc filename.c –o dog
```
this will generate an execuatble file dog from filename.c

Generate all intermediate files in build process along with the executable.
```console
 $ gcc -Wall -save-temps filename.c –o filename 
```


## Building a C program: behind the scenes

The C program goes through the following phases during build:
   * Pre-processing
   * Compilation
   * Assembly
   * Linking

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230404112946/Compilation-Process-in-C.png" height="350"> 

   
create a source file **filename.c** and generate all intermediate files along with the executable.

```console
 $ gcc -Wall -save-temps filename.c –o filename 
```
The following screenshot shows all generated intermediate files.

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230406112742/c-compilation-intermediate-files.webp">

Let us one by one see what these intermediate files contain.
## 1. Pre-processing

This is the first phase through which source code is passed. This phase includes:

    * Removal of Comments
    * Expansion of Macros
    * Expansion of the included files.
    * Conditional compilation

The preprocessed output is stored in the filename.i

Let’s see what’s inside filename.i 
```console
$ vi filename.i 
```
In the above output, the source file is filled with lots and lots of info, but in the end, our code is preserved. 

* printf contains now a + b rather than add(a, b) that’s because macros have expanded.
* Comments are stripped off.
* #include<stdio.h> is missing instead we see lots of code. So header files have been expanded and included in our source file.
## 2. Compiling

The next step is to compile filename.i and produce an; intermediate compiled output file filename.s. This file is in assembly-level instructions. Let’s see through this file using $nano filename.s  terminal command.

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230406112833/c-compilation-assembly-code.webp">

The snapshot shows that it is in assembly language, which the assembler can understand.

## 3. Assembling

In this phase the filename.s is taken as input and turned into filename.o by the assembler. This file contains machine-level instructions. At this phase, only existing code is converted into machine language, and the function calls like printf() are not resolved. Let’s view this file using 
$vi filename.o 

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230406112945/c-compilation-binary-file_1.webp">

## 4. Linking

This is the final phase in which all the linking of function calls with their definitions is done. Linker knows where all these functions are implemented. Linker does some extra work also, it adds some extra code to our program which is required when the program starts and ends. For example, there is a code that is required for setting up the environment like passing command line arguments. This task can be easily verified by using $size filename.o and $size filename. Through these commands, we know how the output file increases from an object file to an executable file. This is because of the extra code that Linker adds to our program. 


## note:
- GCC is not just a compiler it is a colllection of toolchains that will help to convert high level lanuguages to binary.
- GCC tool chains include preprocessor,compiler,assembler and linker.
- Assembly file can be used "s" or "S" extensions.lower case s is generated as the output of compilation.upper case S is used when we are writing a assembly file. usually this file is fed to preprocessor before feeding to assembler. (assembly files may have #include sections)