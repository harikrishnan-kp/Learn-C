# Dynamic memory allocation 
The process of allocating memory during the execution time is called as dynamic memory allocation
- When to use dynamic memory allocation
    - When you don’t know in advance how much memory you'll need at compile time.
    - When you want flexible, runtime-sized data structures.
- This will overcome disadvantages of static memory allocation
- This method use heap
- We need pointers to access this dynamically allocated memory
- Dynamic memory allocation is possible in C by using 4 library functions provided by <stdlib.h> library. They are
    - malloc()
    - calloc()
    - realloc()
    - free()
## malloc()
The malloc() (stands for memory allocation) function is used to allocate a single block of contiguous memory on the heap at runtime. The memory allocated by malloc() is uninitialized, meaning it contains garbage values (A garbage value in C refers to the random, leftover data already present in a memory location before your program writes anything to it).
```bash 
# Synatx
malloc(size);
```
- where size is the number of bytes to allocate.
- This function returns a void pointer to the allocated memory that needs to be converted to the pointer of required type to be usable. If allocation fails, it returns NULL pointer.
