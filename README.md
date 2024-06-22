![image](https://github.com/izcoser/mips-computer/assets/76838137/dc484198-4274-43b8-abf6-ff51cb0b7122)# Mips Computer

Mips Computer is a computer architecture project to simulate a simple virtual computer using the MIPS instruction set.

The computer contains:

* A program counter;
* An 16M x 32 bit instruction memory;
* An ALU with adder, subtractor, AND, OR and NOR gates. The ALU outputs both the result and a zero flag bit;
* A memory module with 4x 16M x 8 bit readable and writable RAM;
* 32 registers of 32 bits each;
* Controllers such as an ALU controller and a general controller, which operate on slices of the instruction to determine the ALU operation and flags such as branch, write to register, read memory.
* Supporting components such as instruction splitters, joiners, sign extenders and shifters.
* A terminal from the Logisim Evolution library only for outputting the result of whatever is calculated in the MIPS processor.

To test the computer, I have written some programs directly into the instruction ROM. The program below writes "Hello World.\n" to the terminal in an infinite loop.

![MIPS instructions](https://github.com/izcoser/mips-computer/blob/master/images/instruction_memory.jpg?raw=true)

The instructions above are:

| Instruction          | 32 bit binary             | Hex        | Action          |
| -------------------- | ------------------------- | ---------- | --------------- |
| addi r1, r0, 0x48    | 00100000000000010000000001001000 | 0x20010048 | 'H' to $1      |
| addi r2, r0, 0x65    | 00100000000000100000000001100101 | 0x20020065 | 'e' to $2      |
| addi r3, r0, 0x6c    | 00100000000000110000000001101100 | 0x2003006C | 'l' to $3      |
| addi r4, r0, 0x6c    | 00100000000001000000000001101100 | 0x2004006C | 'l' to $4      |
| addi r5, r0, 0x6f    | 00100000000001010000000001101111 | 0x2005006F | 'o' to $5      |
| addi r6, r0, 0x20    | 00100000000001100000000000100000 | 0x20060020 | ' ' to $6      |
| addi r7, r0, 0x57    | 00100000000001110000000001010111 | 0x20070057 | 'W' to $7      |
| addi r8, r0, 0x6f    | 00100000000010000000000001101111 | 0x2008006F | 'o' to $8      |
| addi r9, r0, 0x72    | 00100000000010010000000001110010 | 0x20090072 | 'r' to $9      |
| addi r10, r0, 0x6c   | 00100000000010100000000001101100 | 0x200A006C | 'l' to $10     |
| addi r11, r0, 0x64   | 00100000000010110000000001100100 | 0x200B0064 | 'd' to $11     |
| addi r12, r0, 0x2e   | 00100000000011000000000000101110 | 0x200C002E | '.' to $12     |
| addi r13, r0, 0x0a   | 00100000000011010000000000001010 | 0x200D000A | '\n' to $13    |
| j 0                  | 00001000000000000000000000000000 | 0x08000000 | Go to start. |

<sup><sub>I asked an LLM to generate this table based on some plaintext notes I had, if anything is wrong blame it on hallucinations.</sub></sup>

The result is:

![image](https://github.com/izcoser/mips-computer/blob/master/images/hello_world.jpg?raw=true)

Other programs have been written for this virtual processor such as a Fibonacci sequence generator, as shown in trab5fib.circ, however it does not output to the terminal.
