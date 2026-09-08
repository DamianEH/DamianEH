## Instructions:  
- ADD (Operate[^1]) = 0001  
    - Adds two numbers
    - ADD DR[^2] (0 00) - SR[^3]1(Source) SR2
    - ADD DR SR1 1 IMM5
    - ADD DR, SR1, SR2
    - DR = SR1 + SR2

- AND (Operate) = 0101
    - bitwise boolean and
- NOT (Operate) = 1001
    - bitwise boolean not
- LD* (Movement[^4]) (Load Direct) = 0010
    - Direct/ PC-Relative
    - 0010 DR PCoffset9(Offset Range, how far we want to go into memory to retrieve a value (-256/+255 range) 000000010)  
    - PCOffset9 = Desired Location - Instruction Location - 1  
    - Pointing label sets Registration
    - `LD R1, INIT_X` ; R1 <= MEM(INIT_X)
    - `.FILL (number)` ; fill the next memory address with num
    - Assembler Instruction: LD DR, LABEL
- LDI` (Movement)
    - Indirect
- LDR~ (Movement)
    - Base + Offset (Relative)
- LEA (Movement)
    - Immadiate
    - Does not access memory
- ST* (Movement)
    - ST SR, PCOffset9 
    - ST R0 RESULT ; Store whatever is in R0 at RESULT
    - Result .FILL ___
- STI` (Movement)
- STR~ (Movement)
- BR(n, z, p) (Control[^5])

## Short hand:  
- HALT
- GetC

## Pseudo Ops (Has a dot in front of it):  
- .ORIG
- .END
- .FILL
- .BLKW

## Definitions cont.
- Opcode
        - specifies the instruction type  
- Operands
        - specifies what the instruction acts on

[^1]: Operate = manipulate data directly
[^2]: DR = Destination Register = 001
[^3]: SR = source
[^4]: Movement = Move data between memory and registers
[^5]: Control = change the seq. of the instruction execution 
    (not listed in Instructions: JMP/RET, JSR/JSSR, TRAP, RTI)

Start ; label
LEA object; loads address of object
PUTS ; prints object
BR START ; jumps back to start or other place

object .STRINGZ "\n" ; sets message

### Memory
- Holds data and instructions (MAR and MDR)
### Processing Unit
- Carries out instructions (ALU and TEMP)
### Control Unit
- Sequences and interprets instructions (PC and IR)

### LC3 Instruction Set Architecture
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

