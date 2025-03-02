# Conditional compilation
* `if`
    * Typical Use Case:
        * General-purpose conditional compilation.
        * Often used when a macro might be defined elsewhere (e.g., in a build system or compiler flags), and you want to provide a fallback if it isn't defined.

```console
eg:
    #if !defined (STM32L0) // Code here runs only if STM32L0 is not defined
    #define STM32L0
    #endif
```

* `#ifndef`
    * Typical Use Case: Commonly used in header guards to prevent multiple inclusions of the same header file.

```console
eg:
    #ifndef __STM32L0xx_H // Code here runs only if __STM32L0xx_H is not defined
    #define __STM32L0xx_H
    #endif
```