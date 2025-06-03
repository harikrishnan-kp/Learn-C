in embedded c 
- 0b prefix is using to represent a binary number
- 0x prefix is using to represent a hexadecimal number
- in embedded c programming main function is not needed but when we write a c program to work in an OS its important to use main function.


* stm32 is a 32 bit microcontroller, which means this mcu can process 32 bit data in single instruction cycle, consist of 32 bit wide registers and data buses.
* registers are special type memory locations on mcu.
* usually every peripheral pin of an mcu is conneted to a register in it (we can call it as peripheral registers)
* by modifying register bits can change the mode and state of an output pin
* in stm32 mcu a 32 bit register will controll 16 output pins,ie two bit for every pin
* if we want to controll a pin we need change the 2bits corresponding to the pin
* how to write data to the register ,use pointers
* consider a case when need to controll a pin of mcu, and we know the address of mode reguster,pin controlling bits are 13 and 14
* writing a 32 binary value should be challenging because if we make 13 and 14 as 1 and remaining as 0,this may cause un expected behaviours
* becuase we dont know the default binary state of other pins in that register, and know the details of unwanted pins is inefficient idea
* so it is better not to touch the unwanted bits in that register
* when we try to make 
* Resetting the bits of a peripheral register before setting them to a desired value is a common practice in embedded systems programming to ensure data integrity and consistent behavior
* Resetting ensures a known starting state for the register
* Peripheral registers can contain residual values from a previous configuration or operation (especially after a reset or power-on).
* Failing to clear these bits may cause unintended behavior, as the peripheral could interpret these leftover values as valid configurations.

refference https://www.youtube.com/watch?v=TFr_kb4UWpA

<img src=utils/img/pin_config.png>
<img src=utils/img/reset_bit.png>
<img src=utils/img/set_bit.png>
<img src=utils/img/result.png>



## STM NOTES
* use ctrl + spacebar for auto completion 
* use ctrl for going the source of function definition
* stmcube IDE is linked with stmcubemx,stmcube analyzer and stmcube programmer  

<img src=../utils/stmcube.png>


## important c programming topics in embedded
* pinter
* macros
* bit mainipulation
* variables
* data types
* function
* build
* structure

# Important resources
- linux device drivers :
  - https://embetronicx.com/tutorials/linux/device-drivers/linux-device-driver-part-1-introduction/
  - https://www.apriorit.com/dev-blog/195-simple-driver-for-linux-os
