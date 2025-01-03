![image](https://github.com/user-attachments/assets/329ce228-c942-4ea9-8474-00b52fb88899)![image](https://github.com/user-attachments/assets/b54ef47e-2a28-4a7e-8165-dec91a7ebbb9)# VSDSquadron-Mini-Research-Internship-Program
VSDSquadron Internship

This repository consists of the various tasks and projects that have been assigned as a part of the VSDSquadron-Mini-Research-Internship-Program.

### Task - 1
### --------

Task 1 comprises of two sets labs:

####Lab - 1 
####--------

A C code named sum1ton.c was written and copiled using the gcc compiler and executed in the terminal.The program summed over all the numbers from 1 till the specified n value.
The correspoding code and the its output snippets have been uploaded above and can be found in the files starting with the name Lab 1.

####Lab - 2
####-------
The same code (sum1ton.c) is compiled using the riscv compiler and an output file by name sum1ton.o was generated. This file was disassembled to its assembly language code where the number of instruction used for the "main" section in the code or the main function was obseved and calculated.

A similar process was done after compiling the same code using riscv compiler but replacing "O1" with "Ofast".

The corresponding snippets of the commands and the instructions contained in the main section along with the calculation of the number of instructions have been uploaded above and can be found in the files starting with the name Lab 2.



### Task - 2
### --------

The contents of the assembly language program was displayed agiain for the file by the name sum1ton.o.

The same C code was compiled using a gcc compiler and riscv compiler and the output in both the cases was determined to be the same.

The spike package was also used here to run the output of the program compiled through riscv compiler.

####Lab - 3
####-------

The Object dump consistig of the assembly language code was obtained and the spike debugger was used to make the Program Counter run till the memory address 100b0 and the rest of the programs in the address could be run manually.

The contents of the reistor a2 was were looked at before and after the contents were modified by the lui command which loaded the upper immediate bits (12 - 31) of the registor.

Simiar observation was done on the a0 registor where the add immediate(addi) command was used and hexadecimal addiition was done on the contents of the value stored in the register pointer.


The corresponding snippets of the commands and the instructions used throught Lab 3  can be found in the files by the name Task 2 - Lab 3


### Task - 3
###---------

1) The various RISCV instruction types have beem listed below after going through the RISC-V software documentation. 

![image](https://github.com/user-attachments/assets/61e7882a-7ea2-4f49-926e-b151334292ca)

R-Type Instructions:
•	Used for arithmetic and logical operations involving two source registers, with the result stored in a destination register.
•	Instruction format includes fields for opcode, destination register (rd), two source registers (rs1, rs2), a funct3 field, and a funct7 field for additional operation specification.
•	Common examples: add (addition), sub (subtraction), and (bitwise AND), or (bitwise OR), xor (bitwise XOR), sll (shift left logical), and srl (shift right logical).


#####I-Type Instructions:
•	Used for operations involving an immediate value, such as arithmetic operations with constants, loading data from memory, and controlling program flow.
•	Format includes an opcode, destination register (rd), source register (rs1), funct3 field, and a 12-bit immediate value.
•	Often employed to load data from memory into registers, which is vital for data manipulation and processing.


#####S-Type Instructions:
•	Designed for storing data from registers into memory, facilitating data management in programs.
•	Format includes an opcode, source register (rs1), funct3 field, an immediate value (split into two parts), and a second source register (rs2) containing data to be stored.
•	Essential for writing data back to memory, a critical operation in programs manipulating data.




#####B-Type Instructions:
•	Used for conditional branching, allowing changes in the program’s flow based on specific conditions.
•	Format includes an opcode, two source registers (rs1, rs2) for comparison, a funct3 field to specify the type of comparison, and an immediate value representing the branch target.
•	Examples include beq (branch if equal), bne (branch if not equal), blt (branch if less than), and bge (branch if greater than or equal). 
•	Essential for implementing control structures like loops and conditionals, enabling dynamic program behavior.


#####U-Type Instructions:
•	Used for loading large immediate values into registers, particularly for operations requiring a 20-bit immediate.
•	Format includes an opcode, destination register (rd), and a 20-bit immediate value placed in the upper 20 bits of the register.
•	Examples include lui (load upper immediate) and auipc (add upper immediate to program counter).
•	Often used in combination with other instructions to construct full 32-bit addresses or large constants.


#####J-Type Instructions:
•	Used for unconditional jumps, allowing the program to jump to a specified address in the instruction stream.
•	Format includes an opcode, destination register (rd), and a 20-bit immediate value that specifies the jump target.
•	Primary example: jal (jump and link), which also saves the return address in the destination register.
 



2) The 15 Unique instructions have beem given below.
   1.	addi: Add immediate - adds a constant value to a register. 
   2.	sd: Store double - stores a 64-bit value from a register to memory. 
   3.	li: Load immediate - loads a constant value into a register. 
   4.	jal: Jump and link - jumps to a specified address and saves the return address. 
   5.	ld: Load double - loads a 64-bit value from memory into a register. 
   6.	ret: Return - returns from a function (typically used with jal). 
   7.	mv: Move - copies the value from one register to another. 
   8.	beqz: Branch if equal to zero - branches to a specified address if a register is zero. 
   9.	jalr: Jump and link register - jumps to an address in a register and saves the return address. 
  10.	jr: Jump register - jumps to the address contained in a register. 
  11.	bltz: Branch if less than zero - branches if a register's value is negative. 
  12.	neg: Negate - negates the value in a register. 
  13.	sll: Shift left logical - shifts the bits of a register to the left. 
  14.	and: Bitwise AND - performs a bitwise AND operation between two registers. 
  15.	sub: Subtract - subtracts one register from another. 
  

3) The 32 bit instruction code in the instruction type format for the 15 unique instructions.

   1.	addi (I-type)
    o	Opcode: 0010011
    o	Format: imm[11:0] | rs1 | funct3 | rd | opcode
    o	Example: 000000000001 | 00001 | 000 | 00010 | 0010011 (adds 1 to register x1 and stores in x2)
  2.	sd (S-type)
    o	Opcode: 0100011
    o	Format: imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode
    o	Example: 0000000 | 00010 | 00001 | 011 | 00000 | 0100011 (stores x2 into memory address in x1)
  3.	jal (J-type)
    o	Opcode: 1101111
    o	Format: imm[20] | imm[10:1] | imm[11] | imm[19:12] | rd | opcode
    o	Example: 00000000000000000000 | 00000 | 1101111 (jumps to address)
  4.	ld (I-type)
    o	Opcode: 0000011
    o	Format: imm[11:0] | rs1 | funct3 | rd | opcode
    o	Example: 000000000000 | 00001 | 011 | 00010 | 0000011 (loads from memory into x2)
  5.	mv (Pseudo-instruction, typically translated to addi)
    o	Example: addi rd, rs1, 0
  6.	beqz (B-type)
    o	Opcode: 1100011
    o	Format: imm[12] | imm[10:5] | rs1 | rs2 | funct3 | imm[4:1] | imm[11] | opcode
    o	Example: 000000000000 | 00001 | 00000 | 000 | 00000 | 1100011 (branch if x1 is zero)
  7.	jalr (I-type)
    o	Opcode: 1100111
    o	Format: imm[11:0] | rs1 | funct3 | rd | opcode
    o	Example: 000000000000 | 00001 | 000 | 00010 | 1100111 (jumps to address in x1)

  8.	bltz (B-type)
    o	Opcode: 1100011
    o	Format: imm[12] | imm[10:5] | rs1 | rs2 | funct3 | imm[4:1] | imm[11] | opcode
    o	Example: 000000000000 | 00001 | 00000 | 000 | 00000 | 1100011 (branch if x1 is less than zero)
  9.	sll (R-type)
    o	Opcode: 0110011
    o	Format: shamt | rs2 | rs1 | funct3 | rd | opcode
    o	Example: 00000 | 00010 | 00001 | 001 | 00010 | 0110011 (shift left logical)
 10.	and (R-type)
    o	Opcode: 0110011
    o	Format: funct7 | rs2 | rs1 | funct3 | rd | opcode
    o	Example: 0000000 | 00010 | 00001 | 111 | 00010 | 0110011 (bitwise AND)
 11.	sub (R-type)
    o	Opcode: 0110011
    o	Format: funct7 | rs2 | rs1 | funct3 | rd | opcode
    o	Example: 0100000 | 00010 | 00001 | 000 | 00010 | 0110011 (subtract)




4) The 32 bit pattern for the code FFO1O113
 The binary 32 bit Equivalent of this is 1111 1111 0000 0001 0000 0001 0001 0011.

![image](https://github.com/user-attachments/assets/7af2e31b-c801-4ea9-a705-1807d251425e)

o	The binary representation can be split into fields: 
Opcode (7 bits): The last 7 bits are 00010011, which corresponds to the addi opcode.
rd (5 bits): The next 5 bits are 00010, which corresponds to register x2 (sp).
funct3 (3 bits): The next 3 bits are 000, which indicates the addi function.
rs1 (5 bits): The next 5 bits are 00010, which also corresponds to register x2 (sp).
Immediate (12 bits): The first 12 bits are 111111111111, which is -16 in two's complement.

The instruction ff010113 corresponds to addi sp, sp, -16.










