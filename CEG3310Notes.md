


## Instructions:  
- ADD = 0001
        ADD DR(Destination Register = 001) (0 00) SR1(Source) SR2
        ADD DR SR1 1 IMM5
- AND
- NOT
- LD (Load Direct)
        0010 DR PCoffset9(Offset Range, how far we want to go into memory to retrieve a value (-256/+255 range) 000000010)
        PCOffset9 = Desired Location - Instruction Location - 1
        Pointing label sets Registration
        `LD R1, INIT_X` ; R1 <= MEM(INIT_X)
        `.FILL (number)` ; fill the next memory address with num
- LEA
- ST
        ST SR, PCOffset9 
        ST R0 RESULT ; Store whatever is in R0 at RESULT
        Result .FILL ___
- STI
- STR
- BR(n, z, p)

## Short hand:  
- HALT
- GetC

## Pseudo Ops (Has a dot in front of it):  
- .ORIG
- .END
- .FILL
- .BLKW


### ADD Instructions:  
ADD DR, SR1, SR2
    DR = SR1 + SR2

Start ; label
LEA object; loads address of object
PUTS ; prints object
BR START ; jumps back to start or other place

object .STRINGZ "\n" ; sets message

Memory
- Holds data and instructions (MAR and MDR)
Processing Unit
- Carries out instructions (ALU and TEMP)
Control Unit
- Sequences and interprets instructions (PC and IR)

LC3 Instruction Set Architecture
- 16 bit words and word addressable
    - Each address of memory contans the same amount of memory as 1 word (16 bits = 1 word)
    - Note: a word is the unit of data used by a specific processor
- All instructions are 16 bit and all data are 16 bit words
    - 2's complement integer are the only native data type
- Eight 16 bit gen purpose registers (GPRs) R0-R7
- Three 1 bit status codes (N,Z, P)

`.ORIG x3000`

`ADD R0, R1, R2` ; R0 = R1 + R2

`.END`

`#-1` = formatting

`ADD R4, R4, #-1` ; #-1 = '-1'?
OPCODE DR SR1 Format
0001 100 100 1 11111 (The Binary Instruction)

