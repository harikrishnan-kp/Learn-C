# Keywords
Keywords are reserved words that have predefined meanings in C. These cannot be used as identifiers (variable names, function names, etc). Keywords define the structure and behavior of the program. Since C is case-sensitive, all keywords must be written in lowercase letters; otherwise, the compiler will throw errors.

There are 32 standard keywords in C, they are

|        |          |          |        |
|--------|----------|----------|--------|
| auto   | break    | case     | char   |
| const  | continue | default  | do     |
| double | else     | enum     | extern |
| float  | for      | goto     | if     |
| int    | long     | register | return |
| short  | signed   | sizeof   | static |
| struct | switch   | typedef  | union  |
| void   | unsigned | volatile | while  |

```bash
# Note: The number of keywords may change depending on the version of C you are using. For example, keywords present in ANSI C are 32 while in C11, it was increased to 44. Moreover, in the latest c23, it is increased to around 54.
```
## typedef
The typedef keyword in C is used to create an alias for an existing data type. That is it doesn't introduce a new data type but provides a new name for an existing one. This will help to reduce code complexity.
```bash
# Syntax
    typedef existing_type new_type_name;
```
existing_type: The original data type (e.g., int, struct, unsigned long).
new_type_name: The new alias for the existing type.
```
Example
    typedef unsigned char u1_t;

# usage   
    u1_t value = 255; 
```
- It is possible to use this keyword on pointers and structure
- structure aliasing
    ```bash
    typedef struct { int x; int y; } Point;
    Point p1 = {10, 20};
    ```



    
## TODO
* explain 32 standard keywords and their meaning
* Add Hyper link to keywords given in table to access its explanation easly
* next page button
