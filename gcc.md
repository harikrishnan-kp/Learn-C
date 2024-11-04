# GCC - GNU Compiler Collection
- GCC is not just a compiler it is a colllection of toolchains that will help to convert high level lanuguages to binary.
- GCC tool chains include preprocessor, compiler, assembler and linker.
## how to use GCC
* Build a C file using gcc

```bash
# syntax
    gcc filename.c

# output: 
    a.out
# note: a.out is the default name of final executable file from GCC
```
```bash
examples: 

# build a single C file
gcc hex.c

# Build multiple C files simultaneously
gcc hex.c hello.c
```        
## gcc flags
* -o : This option specifies the name of the output file

```bash
eg:
    gcc main.c -o hi
# input = main.c
# output = hi
```
*  -E: This option tells the GCC to run only the preprocessor only.ie, you will get preprocessor output only. By default, if you don’t use -o, the output will be printed to the terminal.

```bash
eg: 
    gcc -E main.c
# input = main.c
# ouput = you will get preprocessed file on terminal
    gcc -E mani.c -o main.i
# input = main.c
# output = main.i
```
* -c : for creating object files from c file (ie,the  output file of assembler)

```bash
eg:
    gcc -c main.c
# input = main.c
# output = main.o
```
* -save-temp : This flag in gcc tells the compiler to save all intermediate files generated during the compilation process. Normally, GCC deletes these temporary files after compiling.
```bash
eg:
    gcc -save-temps main.c
# input = main.c
# output = main.i, main.s, main.o, a.out

