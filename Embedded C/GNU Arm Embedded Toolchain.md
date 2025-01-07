# GNU Arm Embedded Toolchain
The GNU Arm Embedded Toolchain is a ready-to-use, open-source suite of tools for C, C++ and assembly programming. The GNU Arm Embedded Toolchain targets the 32-bit Arm Cortex-A, Arm Cortex-M, and Arm Cortex-R processor families. The GNU Arm Embedded Toolchain includes the GNU Compiler (GCC) and is available free of charge directly from Arm for embedded software development on Windows, Linux, and Mac OS X operating systems.

## arm-none-eabi-gcc flags
* -mcpu : used to specify the target ARM processor for which the code is being compiled. 
    * if we are using a common header file that is written for many microcontrollers it is necessary to define the taget microcontroller in source file using #define <target name> for linking corresponding header files.
    * by using -mcpu we can avoid editing source file for adding target

```bash 
syntax:
    -mcpu=<processor>
eg:
    -mcpu=cortex-m0plus
    -mcpu=cortex-m3
```

* -I : This flag specifies a directory to be added to the list of directories that the compiler searches for header files.
    * When you use #include in your code, GCC looks in standard directories (like /usr/include) by default, but with -I, you can tell GCC to also look in other directories you specify.

```bash
syntax:
    -I<directory>
eg:
   -I../Core/Inc -I../Drivers/STM32L0xx_HAL_Driver/Inc 
````

* -std : used to specify the C language standard (C11) with GNU-specific extensions for a project being compiled for.
    * gnu11 is a standard based on the C11 (ISO/IEC 9899:2011) standard, useful in embedded systems development where lower-level access to hardware or optimizations are required
    * this variant of C11 allows the use of additional GNU-specific extensions that are not part of the standard C11 specification.
```bash 
syntax:
    -std=<standard>
eg:
    -std=gnu11
    -std=c11 
```

* -g :This flag specifies the level of debug information that should be included in the compiled binary.

```bash 
syntax:
    -g<level of debug information> # level can be 0,1,2,3 etc  
eg:
    -g3
    -g0 
```

* -o : (small o) This option specifies the name of the output file

```bash
syntax: 
    arm-none-eabi-gcc <input file> -o <output file name>
eg:
    arm-none-eabi-gcc main.c -o hi
# input = main.c
# output = hi
```
* -O : (capital O) used to specify the level of optimization in our code .
    * by default gcc do not do optimization.we can control the level of optimization by changing optimization level.
    * note: optimization make debugging difficult
```bash
syntax: 
     -O<optimization level>
eg:
    * arm-none-eabi-gcc -O0 main.c # no optimization (default)
    * arm-none-eabi-gcc -O1 main.c # basic optimization
    * arm-none-eabi-gcc -O2 main.c # more optimizations
    * arm-none-eabi-gcc -O3 main.c # aggressive optimizations
    * arm-none-eabi-gcc -Os main.c # optimize for size
    * arm-none-eabi-gcc -Ofast main.c # fast optimizations, may violate strict standards
