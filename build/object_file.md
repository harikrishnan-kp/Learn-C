# object file (NOT FINALIZED YET)
- object file is an intermediate file generated as the output of assembler during the build process.
- the object code (typically a `.o` or `.obj` file) consists of several sections that contain different types of information.
- These sections are used by the linker to generate the final executable. The key sections in an object file are:

- Text Section (`.text`)
    - Contains the machine code (binary instructions) generated from the C source code.
    - This section is read-only and executed at runtime.
    - Includes functions and code written by the programmer.
- Data Section
This section contains initialized global and static variables. It is further divided into:
    - `.data` (Initialized Data Section)
        - Stores initialized global and static variables (e.g., int x = 10;).
        - Read-write section.
    - `.rodata` (Read-Only Data Section)
        - Stores constant values, including string literals (printf("Hello");).
        - Usually read-only to prevent modification at runtime.
- BSS Section (`.bss`)
    - Stores uninitialized global and static variables.
    - These variables are initialized to zero by the runtime before execution.
    - Does not occupy space in the object file but is allocated memory at runtime.
- Symbol Table (`.symtab`)
    - Contains information about functions, global variables, and their addresses.
    - Useful for debugging and linking but not included in the final executable.
    - Can be viewed using tools like nm or objdump.
- Relocation Table (`.rel.text`, `.rel.data`, etc.)
    - Used for relocating addresses of variables and functions when linking multiple object files.
    - Helps the linker resolve external references (e.g., function calls to external libraries).
- Debugging Information (`.debug`)
    - Only present if compiled with debugging flags (-g in GCC).
    - Stores source-level debugging information, such as variable names and line numbers.
    - Used by debuggers like gdb.
- Other Sections
    - `.comment` – Stores compiler version and build information.
    - `.note`– Metadata like build ID, OS version, etc.
    - `.plt` (Procedure Linkage Table) – Used for dynamically linking functions at runtime.

## Viewing Object File Sections
You can inspect an object file's sections using:
```
    objdump -h file.o (Linux)
    readelf -S file.o (Linux)
    nm file.o (Shows symbols)
```

## types of object files
- relocatable: non executable file that need to be linked into another file
- executable: executable binary program
- shared object:these are shared libraries (for dynamic linking)
