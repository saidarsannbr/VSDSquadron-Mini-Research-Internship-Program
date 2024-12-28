# VSDSquadron-Mini-Research-Internship-Program
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
