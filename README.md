# VSD_internship
## TASK 1
### Installation of RISC V toolchain was done successfully.
### The task was to compile a C code that counts the sum of numbers from 1 to n and to run this program using a RISC V simulator.</p>

Firstly,I installed the text editor Leafpad using the command 'sudo apt-get install leafpad'.

Then,using the command 'leafpad sum1ton.c',I created a file in leafpad to write the following C code which calculates the sum of numbers from 1 to n:

![C CODE](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/e55368f9-35f5-4efc-9223-d76f71322a50)

I ran the program for n=5 using the following commands and obtained the result as expected:

![sumfrom1to5](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/808eb2ae-b3cb-4063-a1bd-9ec898765771)

I ran the program again but with n=100:

![sumfrom1to100](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/a951de54-0afd-4a13-8c8f-a1d40aa01f14)

Next task was to run the above program using a RISC V simulator as follows:
![O1](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/9d657424-ec9e-4aab-bd17-613bc19fa511)

I used the command 'riscv64-unknown-elf-objdump -d sum1ton.o | less' to open the assembly level instructions and searched for 'main'.As is evident from the image,it consists of 15 instructions.
![15instructions_O1](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/21d9cccf-2510-48fa-b5dd-46eb9cd4e4dc)

Instead of O1,I ran the program using Ofast as follows:
![Ofast](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/7d5533da-74bd-4920-b1be-9e24136c24b0)

Using the command 'riscv64-unknown-elf-objdump -d sum1ton.o | less' again and seaching for 'main' gives the following image.As is evident from the image,it consists of 12 instructions.
![12instructions_Ofast](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/8a45cdc2-5ac3-424a-9e07-1818170c1684)





