# Operators in C
* An operator in C can be defined as the symbol that helps us to perform some specific mathematical, relational, bitwise, conditional, or logical computations on values and variables
* The values or variables on which the operators perform it's operation is called `operands`.

 
```bash
Eg:
    Consider an expression,
                         a = x+y;
# Here variables x and y are the operands in which data need to be manipulated is stored 
#  + and = symbols are operators
```
## Types of operators
Depending on the number of operands that an operator can act upon, operators can be classified as follows:
1. **Unary Operators**: Those operators that require only a single operand to act upon are known as unary operators
    * `Increment operator`
    * `Decrement operator`
    * `Unary plus and minus`
    * `sizeof Operator` (need more data)
2. **Binary Operators**: Those operators that require two operands to act upon are called binary operators
    * `Arithmetic operator`
    * `Logical operator`
    * `Relational operator`
    * `Assignment operator`
    * `Bit wise operator`
3. **Ternary Operators**: The operator that requires three operands to act upon is called the ternary operator. 
    * `Conditional operator`(need more data)

4. there are some **Special operators** which cant categeries with the above,they are
    * `comma operators`(need more data)
    * `cast operator`(need more data)
    * `dot and arrow operator`
    * `addressof (&) and Dereference (*) Operators`

## Increment operator

|Symbol| Operator  | Description              |
|:----:|:----------|:-------------------------|
|  ++  | increment |used a to Increase the value of the operand by 1|

based on how we use the this operator in an expression, the increment operators are divided into two
1. `pre increment operator`
    * The value of the variable is incremented before it is used in the expression.
    * The incremented value is the one that participates in the expression.
    ```bash
    Syntax:
        ++operand
    ```
    ```
    Example:
        #include <stdio.h>
        int main() {
            int x = 5;
            int y = ++x;  // Increment x first, then assign to y
            printf("x = %d, y = %d\n", x, y);
            return 0;
        }
    ```
    ```
    output:
        x = 6, y = 6
    ```
2. `post increment operator`
    * The current value of the variable is used in the expression before it is incremented.
    * The increment happens after the value is used.
    ```bash
    Syntax:
        operand++
    ```
    ```
    Example:
        #include <stdio.h>
        int main() {
            int x = 5;
            int y = x++;  // Assign x to y first, then increment x
            printf("x = %d, y = %d\n", x, y);
            return 0;
        }
    ```
    ```

    Output:
        x = 6, y = 5
    ```
## Decrement operator

|Symbol| Operator  | Description              |
|:----:|:----------|:-------------------------|
|  --  | decrement |used a to decrease the value of the operand by 1|

based on how we use the this operator in an expression, the decrement operators are divided into two
1. `pre decrement operator`

    ```bash
    Syntax:
        --operand
    ```
2. `post decrement operator`

    ```bash
    Syntax:
        operand--
    ```
these two works in the same way as pre increment and post increment operators

## Unary plus and minus
* The unary plus (+) and unary minus (-) operators are commonly used in C to indicate the sign of a value.

|Symbol| Operator  | Description              | Syntax        |  eg |
|:----:|:----------|:-------------------------|:-------------:|:---:|
| +    | unary Plus| Used to specify the positive values  | +operand |+x  |
| -    |unary minus| Flips the sign of the value  | +operand | -x |


* The unary plus operator is rarely used because it does not change the value of the operand. It explicitly states that the value is positive.
* The unary minus Commonly used to negate values

## Sizeof Operator
sizeof is much used in the C programming language. It is a compile-time unary operator which can be used to compute the size of its operand. The result of sizeof is of the unsigned integral type which is usually denoted by size_t.Basically, the sizeof the operator is used to compute the size of the variable or datatype.
```
Syntax:
    sizeof (operand)
```
## Arithmetic operator
Arithmetic operators are the symbols that tells the computer to perform arithmetical operations on operands

|Symbol| Operator  | Description              | example       |
|:----:|:----------|:-------------------------|:-------------:|
| +    | Plus      | Adds two numeric values  | a + b         |
|  -   | Minus     | Subtracts right operand from left operand | a – b |
| *    | Multiply  | Multiply two numeric values   | a * b |
| / | Divide | Divide two numeric values ( Inherently truncates the fractional part ) | a / b |
| % | Modulus |Returns the remainder after diving the left operand with the right operand | a % b |   

## Logical operator (need re structuring table beacause of this logical or symbol)

Symbols that tells the computer to perform logical operations(like AND,OR, etc)

| operators |   Name   |     Meaning          |  Example(assume A=1,C=0)|
|:---------:|:---------|:---------------------|:-----------------------:|
| &&        |Logical AND| output is true If both operands are non zero| A&&C, Output will be false|
|   ||       |Logical OR| output will be true If any one of the operand is one | A||C, Output will be true |
|   !       |Logical NOT|using to reverse the output | !(A&&C), Output will be true |

## Cast Operator
Casting operator is a special operator that forces one data type to be converted into another. For example, float to int
```
Syntax:
    (new_type) operand;
eg:
    y = (int) x;

```
you will study more use case of this operators in `type casting`.

## dot (.) and arrow (->) Operators
* Member operators are used to reference individual members of classes, structures, and unions.
* The dot operator is applied to the actual object. 
* The arrow operator is used with a pointer to an object.
* you will understand this more as you learn `structure and union in C`
```bash
Syntax:
    structure_variable . member; 
    structure_pointer -> member;   #for poniters
```
## Addressof (&) and Dereference (*) Operators
* These operators are used in association with pointers in C 
* Pointer operator & returns the address of a variable. For example &a; will give the actual address of the variable.
* The pointer operator * is a pointer to a variable. For example *var; will pointer to a variable var. 
* you will understand this more when we discuss `pointers in C`

## Operator Precedence and Associativity in C
