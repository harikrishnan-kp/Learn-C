# **Macros and its types in C**
- A macro is a piece of code in a C program that is replaced by the value of the macro. 
- Macro is defined by `#define` directive. Whenever a macro name is encountered by the preprocessor, it replaces the name with the definition of the macro. 
- Macro definitions do not need a semi-colon termination.

```bash
syntax
	#define token value
 ```
```console
Example 
	#define date 31
```       
- `#define date 31` means that everywhere the preprocessor sees the token date in the code, it will replace it with 31 before the actual compilation process begins.
- This substitution is purely textual and occurs before the compiler sees the code. As a result, date  doesn't have a type and doesn't occupy memory as a variable.

## **Types of macros in c**
 - `Object like macros` 
 - `Chain macros`
 - `Function like macros`
 - `Multi-Line Macros`

### **Object-Like Macros**
It is popularly used to replace a symbolic name with a numerical/variable represented as a constant.

```console
	#include <stdio.h>
	#define DATE 31
	int main()
	{
     	printf("Lockdown will be extended" " upto %d-MAY-2020",DATE);
      	return 0;
	}


output = Lockdown will be extended upto 31-MAY-2020
```
	

### **Function-Like Macros**
These macros are the same as a function call. It replaces the entire code instead of a function name. Pair of parentheses immediately after the macro name is necessary. If we put a space between the macro name and the parentheses in the macro definition, then the macro will not work. 
A function-like macro is only lengthened if and only if its name appears with a pair of parentheses after it. If we don’t do this, the function pointer will get the address of the real function and lead to a syntax error.
The macros can take function like arguments, the arguments are not checked for data type. For example, the following macro INCREMENT(x) can be used for x of any data type.

```
	#include <stdio.h>
	// Macro definition
	#define AREA(l, b) (l * b)

	int main()
	{
	// Given lengths l1 and l2
	int l1 = 10, l2 = 5, area;

	// Find the area using macros
	area = AREA(l1, l2);
	printf("Area of rectangle" " is: %d",area);
	return 0;
	}
 
output: Area of rectangle is: 50
```
```console
	#include <stdio.h>
	// Function-like Macro definition
	#define min(a, b) (((a) < (b)) ? (a) : (b))
 
	int main()
	{
	// Given two number a and b
	int a = 18;
	int b = 76;		
	printf("Minimum value between" " %d and %d is %d\n",a, b, min(a, b));
	return 0;
	}

output: Minimum value between 18 and 76 is 18
```
Using a macro without parentheses can lead to incorrect results.
```
#define MULTIPLY(a, b) a * b  // No parentheses
int result = MULTIPLY(2 + 3, 4); 

output:
	Expands to 2 + 3 * 4 = 14 (wrong)
```
Corrected Macro:
```
#define MULTIPLY(a, b) ((a) * (b)) // Parentheses added
int result = MULTIPLY(2 + 3, 4); 

output:
	Expands to (2 + 3) * (4) = 20
```
### **Chain Macros** 
Macros inside macros are termed chain macros. In chain macros first of all parent macro is expanded then the child macro is expanded.

``` console
	 // C program to illustrate macros
	 #include <stdio.h>

	 // Macro definition
	 #define INSTAGRAM FOLLOWERS
	 #define FOLLOWERS 138

	 // Driver Code
	 int main()
	 {
	// Print the message
	printf("Geeks for Geeks have %dK"" followers on Instagram",INSTAGRAM);
  	return 0;
	 }

	output :Geeks for Geeks have 138K followers on Instagram
```

### **Multiline macros**
An object-like macro could have a multi-line. So to create a multi-line macro you have to use backslash-newline.

```console
	#include <stdio.h>
	// Multi-line Macro definition
	#define ELE 1, \
			    2, \
			    3
	// Driver Code
	int main()
	{
	// Array arr[] with elements
	// defined in macros
	int arr[] = { ELE };

	// Print elements
	printf("Elements of Array are:\n");

	for (int i = 0; i < 3; i++) {
	printf("%d ", arr[i]);
	}
	return 0;
	}

output : Elements of Array are: 1  2  3
```
## **Predefined macros**
Predefined macros in C are built-in macros provided by the compiler. They are automatically available and do not require explicit definition.

some predefined macros
- `__FILE__` :  holds the file name of the currently executing program
- `__LINE__` : contains the current line number of the program in the compilation. compiler use this to generates error messages during compilation.
- `__DATE__` : it returns the date at which the program was compiled
- `__TIME__` : gives the time at which program was compiled
- `__STDC__` : Defined if using a standard C compiler
- `__func__` : to print the current function name executing.

for more details visit [Predefined Macros in C](https://www.geeksforgeeks.org/predefined-macros-in-c-with-examples/) 

## **variables vs macros**
`#define DATE 31` is a macros and `int DATE = 31;` is a variable

**Key Differences between macros and variables**
- Scope and Lifetime: 
	- Macro: #define DATE 31 is valid throughout the file from the point of definition, unless undefined using #undef. It has no scope and lifetime in the conventional sense.
	- Variable: int DATE = 31; follows normal variable scoping rules and its lifetime is governed by where it is defined (e.g.,local, global, etc.).
- Type and Memory:
	- Macro: DATE is not typed and doesn't occupy memory.
	- Variable: DATE is an int and occupies memory.
- Debugging and Maintenance:
	- Macro: Can be harder to debug since it’s a plain text replacement and the preprocessor error messages can be less clear.
	- Variable: Easier to debug as it is a regular variable with a type, and the debugger can inspect its value.
- Modification:
	- Macro: Cannot be changed at runtime.
	- Variable: Can be modified at runtime.
- When to Use Each:
	- Use #define for constants that you don't expect to change and when you need simple text substitution.
 	- Use a variable declaration (int DATE = 31;) when you need a typed constant or a value that can be modified during the program execution.
## FAQ
* Can We Define a Macro Without a Value?
	
	Yes! In C, you can define a macro without assigning it a value using #define. This is useful for conditional compilation and feature toggling.
	```
	eg:
		#include <stdio.h>
		#define DEBUG  // Define macro without value

		int main() {
		#ifdef DEBUG
			printf("Debug mode is enabled.\n");
		#endif
			return 0;
		}
	```