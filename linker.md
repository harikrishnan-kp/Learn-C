# linker script
* linker script is a text file which explains how different sections of object files should be merged to create an executable file
* linker script also describe the memory layout of the microcontroller
    * it define code and data memory addresses and size information 
    * it define the starting address and size  of flash and RAM
* linker scripts are written in GNU linker command language
* GNU linker script has a file extension of .ld

## linker script commands
* ENTRY
* MEMORY
* SECTIONS
* KEEP
* ALIGN
* AT

### MEMORY
<img src="img & supporting docs/linkermem.png">

# linker and locator
linker and locator combination assigns unique absolute addresses to different sections of output file by referring to address information mentioned in the linker script

Example linker script written for B-L072Z-LRWAN1 can be found [here]("img & supporting docs/STM32L072CZYX_FLASH.ld")