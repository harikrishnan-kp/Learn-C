# make
make is a build automation tool commonly used in software development to:
* Compile and link source code into executable programs.
Manage dependencies between files.
* Automate repetitive tasks like testing, deployment, or cleanup.

## Usage
* Make is  very usefull when we are building a big project with multiple source files
* Manual building of this project may required a big terminal command with lots flags and options to tool chain.
* one big terminal command make it hard to read, understand and maintain.
* it is also inefficient, beacause it will build every file in the project eachtime, eventhough we modified only one or two source files.
* inorder to overcome these problems, we can use make.

## Key Features of make
* Dependency Management : Automatically checks if a file is out of date by comparing timestamps.Only recompiles what’s necessary, saving time.
* Automation : Automates complex build processes like compiling source code, linking, cleaning, and testing.
* Cross-Platform : While originally designed for Unix-like systems, make is available on many platforms.
* Extensibility : Supports variables, functions, and conditionals to create dynamic and reusable build scripts.

## Makefile
* A Makefile is a plain text file that contains the rules and instructions that **make** uses to build a project
* make file describes how to get a certain output from a set of inputs
* it will organize and keep track of our build process

make reads a set of rules and dependencies from a Makefile, and determines which parts of a project need to be rebuilt. It then executes the appropriate commands to update only the necessary parts.

## Why Use make and Makefiles?
* Efficiency: Rebuilds only what’s necessary, saving time.
* Consistency: Standardizes the build process.
* Flexibility: Can handle projects with multiple files,directories, and configurations.

## Structure of Makefile
<img src=../../utils/makefile.png width=450>

## Example Makefile
```bash
all: program

program: main.o utils.o
    gcc main.o utils.o -o program

main.o: main.c
    gcc -c main.c -o main.o

utils.o: utils.c
    gcc -c utils.c -o utils.o

clean:
    rm -f *.o program

# Running make starts with the all target, which depends on program.
# The program target depends on main.o and utils.o.
# make recursively resolves dependencies, compiling the .c files into .o files before linking them.
```

## Rule
In a Makefile, a rule is a fundamental construct that tells make how to build a target. A rule defines:
* What to build (the target)
* What it depends on (the dependencies)
* How to build it (the commands to execute)
```bash
# Structure of a Rule
target: dependencies
    commands

# target: The name of the file or action to be created or executed
# dependencies: Files or targets that must exist or be up-to-date before the target can be created.
# commands: Shell commands that make executes to build the target

# eg:
    program: main.o utils.o
        gcc main.o utils.o -o program
```
## Types of Rules
1. **Explicit Rules** : Define how to build specific target with it`s dependencies and commands 
```bash
# eg:
    main.o: main.c
        gcc -c main.c -o main.o
```
2. **Implicit Rules** : This type of rules Use built-in commands for building targets. usually using on common file types (e.g., .c to .o)
```bash
# eg: 
    main.o: main.c

# make run the equivalent of gcc -c main.c -o main.o.
```
3. **Pattern rules** : Used to define rules for multiple targets with similar structure.
```bash 
# eg: 
    %.o: %.c
        gcc -c $< -o $@

# % is a wildcard matching filenames
# $< is the first dependency (e.g., main.c)
# $@ is the target (e.g., main.o).
# $^ is the source
```
4. **Phony Rules** : Used to define tasks that don’t generate files (e.g., clean, all)
```bash
# eg:
    .PHONY: clean
    clean:
        rm -f *.o program
```

## where does the execution start in make file
* By default makefile execution start with the first rule by building it`s target
* and then recursively solve other rules
* usually **all** is used as the first target in the makefile, it provides a standardized, user-friendly way to build an entire project.
* additionally there is an option for users to specify which target need to be executed first.
```bash 
eg: make hi
```
## Variables
varibles are use to store values in makefile
* as per standard all varible names are in capital format and declared at the top of make file 
* there are certain rules regarding variable naming in make file

```bash
# Declare and initialize a varible in makefile.
syntax:
    variable_name = value to stored
eg:
    SRC = main.c

# how to access the value stored in a varible
eg:
    OBJ = $(SRC)    

# store a list of values in variable
syntax: 
    varibale_name = value1 value2 value3 ...
eg:
    SRC = main.c hi.c hello.c
```
## Some build in functions in make

1. **addprefix** : function in make is used to add a prefix to each item in a list. It's a powerful and commonly used function to manipulate lists of file paths, such as source files or include directories.
```bash
# syntax :
    $(addprefix prefix, list)

# prefix: The string to be added at the beginning of each item in the list.
# list: A space-separated list of items to which the prefix will be added.
```
```bash
# eg :
    INCLUDE_DIRS = include lib/include
    INCLUDES = $(addprefix -I, $(INCLUDE_DIRS))

# Result: INCLUDES = -Iinclude -Ilib/include
```
2. **addsuffix** : function in make is used to add a suffix to each item in a list
```bash
# syntax
    $(addsuffix suffix, list)
# eg:
    SRC = main utils
    OBJ = $(addsuffix .o, $(SRC))
# result: OBJ = main.o utils.o    
```
3. **foreach** : The construct $(foreach dir, $(INC_DIR), ...) in a Makefile is a loop that iterates over a list of items
```bash
# syntax : 
    $(foreach var, list, text)

# var: The loop variable that takes on the value of each item in the list.
# list: A space-separated list of items to iterate over.
# text: The operation or text to apply for each iteration. This can include references to the loop variable var.
```


# Refferences 
<img src=../../utils/buildcommand1.png>

<img src=../../utils/buildcommand2.png>

## notes
* make can be used for flashing too
* Cmake is also similar to make, but advanced than make.
* Cmake can generate make files