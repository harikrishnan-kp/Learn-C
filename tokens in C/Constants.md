# Constants
Constants are fixed values used in a C program. These values do not change during the execution of the program. Constants can be integers, floating-point numbers, characters, or strings.
```
syntax:
    const datatype nameOfConstant;
```    
```
eg:  
    #include <stdio.h>  
    int main() {
    
        // 'MAX_VALUE' is a constant that holds a fixed value
        const int MAX_VALUE = 100;  
        printf("%d", MAX_VALUE);
        return 0;
    }
```
