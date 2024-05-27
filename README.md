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



## TASK 2
RISC V has the following 6 basic instruction types:

1.R Type

2.I Type

3.S Type

4.U Type

5.B Type

6.J Type

![image](https://github.com/SanidhyaBaheti/VSD_internship/assets/65732300/2b9ef311-3187-4b37-99be-1779b1f16f6d)

### R Type:

It is used for operations that set a destination register rd to the result of an arithmetic, logical or shift operation applied to source registers rs1 and rs2.

### I Type:

It is used to encode instructions with a signed 12-bit immediate operand with a range of [−2048..2047], an rd register, and an rs1 register.It is used for operations such as arithmetic operations, load instructions, and some control instructions.

### S Type:

It is used to encode instructions with a signed 12-bit immediate operand with a range of [−2048..2047], an rs1 register, and an rs2 register.It is used for store operations, where data from a register is stored in memory

### U Type:

It is used for instructions that use a 20-bit immediate operand and an rd destination register.It is used typically for constructing larger constants or for addressing.

### B Type:

It is used for branch instructions that require an even immediate value that is used to determine the branch target address as an offset from the current instruction’s address.It is used for conditional branch instructions, which alter the flow of control based on the result of a comparison.

### J Type

It is used to encode the jal(jump and link) instruction with an immediate value that determines the jump target address. It is similar to the U-type, but the bits in the immediate operand are arranged in a different order.It is used for unconditional jump instructions, which alter the flow of control unconditionally.

### Identifying instruction type and 32 bit code:
#### 1. ADD r6,r2,r1:

R Type

code : 0000000 00001 00010 000 00110 0110011

#### 2. SUB r7,r1,r2:

R Type

code: 0100000 00010 00001 000 00111 0110011

#### 3. AND r8,r1,r3:

R Type

code: 0000000 00011 00001 111 0100 0110011

#### 4. OR r9,r2,r5:

R Type

code: 0000000 00101 00010 110 01001 0110011

#### 5. XOR r10,r1,r4:

R Type

code: 0000000 00100 00001 100 01010 0110011

#### 6. SLT r11,r2,r4:

R Type

code: 0000000 00100 00010 010 01011 0110011

#### 7. ADDI r12,r4,5:

I Type

code: 000000000101 00100 000 01100 0010011

#### 8. SW r3,r1,2:

S Type

code: 0000000 00010 00001 010 00011 0100011

#### 9. SRL r16,r14,r2:

R Type

code: 0000000 00010 01110 101 10000 0110011

#### 10. BNE r0,r1,20:

B Type

code: 0000000 00001 00000 001 10100 1100011

#### 11. BEQ r0,r0,15:

B Type

code: 0000000 0000 00000 000 11110 1100011

#### 12. LW r13,r1,2:

I Type

code: 000000000010 00001 010 01101 0000011

#### 13. SLL r15,r1,r2:

R Type

code: 0000000 00010 00001 001 01111 0110011

