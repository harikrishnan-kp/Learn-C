# Memory Layout of C Programs
The memory layout of a program refers to how the program is stored in the computer memory(RAM) during its execution. A typical memory representation of C program consists of following sections.
1. Text segment
2. Initialized data segment
3. Uninitialized data segment (bss)
4. Stack
5. Heap

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20250122155858092295/Memory-Layout-of-C-Program.webp">

## Text Segment
- Also known as a `code` segment. 
- This segment of memory stores executable instructions in the program.
- Text segment is sharable so that only a single copy needs to be in memory for frequently executed programs.
- This segment is often read-only and stored in the lower part of the memory to prevent accidental modification of the code while the program is running.
## Initialized Data Segment
- Simply called the `Data` Segment.
- Occupies a memory space just above the text segment.
- Contains the global variables and static variables that are initialized by the programmer.
```bash
# Example
// Global variable
int a = 10;

// Static variable
static int b = 20;
```
## Uninitialized Data Segment (BSS)
- often called the `bss`(Block Started by Symbol) segment.
- Occupies a memory space just above the initialized data segment.
- This section stores the global and static variables that are not initialized by the programmer.
- These variables are automatically initialized to zero at runtime by the operating system.
```
# Example
// Global variable
int a;

// Static variable
static int b;
```
## Heap Segment
- Heap segment is where dynamic memory allocation usually takes place.
- The heap area begins at the end of the BSS segment and grows towards the larger addresses from there.
- It is managed by functions such as malloc(), realloc(), and free() which may use the brk and sbrk system calls to adjust its size.
## Stack Segment
- The stack segment is located in the higher addresses of the memory and grows towards the lower addresses from there.
- The stack is a region of memory used for local variables and function call management.
- Each time a function is called, a stack frame is created in stack segment.
    - The set of values pushed for one function call is termed a `stack frame`. This contain local variables, function parameters, and return addresses.
    - Each time a recursive function calls itself, a new stack frame is used, so one set of variables doesn’t interfere with the variables from another instance of the function.
## Note
when stack and heap pointer meet, free memory of the program is said to be exhausted.
