# Memory Allocation in C
Compiler convert c source into obj. it separate code into sections .text .bss etc(depends on file format)
- Static memory allocation
- Automatic memory allocation
- Dynamic memory allocation
## Static memory allocation
The process of allocating memory for a program during the build process is called as static memory allocation.
- We have to declare the required size of memory for each segment in the code.
- Once declared we can`t change it during execution time.
- Disadvantages
  - Consider a situation in which we need to store some random no.of elements in a array during run time. we have no idea about the number of elements and the size of array required to store the elements.but we have to declare the array.
  - If we declare array with size less than requirement, stack over flow occurs. if the size of array is larger than requirements, then we are wasting memory. 
## Dynamic memory allocation 
The process of allocating memory during the execution time is called as dynamic memory allocation
- This will overcome disadvantages of static memory allocation
- This method use heap
- There are some built in functions for this operation
    - malloc()
    - calloc()
    - realloc()
    - free()
- We need pointers to access this dynamically allocated memory
