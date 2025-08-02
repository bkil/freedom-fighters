# FOSS home made processors

## Minimal FPGA

### howerj lfsr-vhdl

* https://github.com/howerj/lfsr-vhdl
* https://en.wikipedia.org/wiki/Linear-feedback_shift_register#Uses_as_counters

> This project contains a CPU written in VHDL for an FPGA using a Linear Feedback Shift Register (LFSR) instead of a Program Counter, this was sometimes done to save space as a LFSR requires fewer gates than an adder, however on an FPGA it will make very little difference as the units that make an FPGA (Slices/Configurable Logic Blocks) have carry chains in them. The saving would perhaps be more apparent if making the system out of 7400 series ICs, or if laying transistors out by hand. The system contains a fully working Forth interpreter. The CPU only occupies 27 slices [85 LUTs], which is only a little larger than the bit-serial CPU and this 16-bit CPU is much faster. Instructions: XOR, AND, LLS1, LRS1, LOAD, STORE, JUMP, JUMPZ. The INDIRECT flag determined whether bits 0 to 11 are treated as a value (not set) or an address (INDIRECT is set).

### howerj bit-serial

* https://github.com/howerj/bit-serial
* https://en.wikipedia.org/wiki/Bit-serial_architecture

> A bit-serial CPU written in VHDL, with a simulator written in C. This allows the CPU itself to be a lot smaller, the penalty is that it is a lot slower. The 16-bit CPU itself is called bcpu. The core is tiny at just about 23 Slices / 76 LUTs. The test program includes a fully working Forth interpreter. The CPU is lacking features required to support higher level programming (such as function calls). The CPU has three registers including the accumulator, the other two are the program counter and a flags register. The CPU has 16 operations, each instruction consists of a 4-bit operation field and a 12-bit operand: OR, AND, XOR, ADD, LSHIFT, RSHIFT, LOAD, STORE, LOADC, STOREC, LITERAL, UNUSED, JUMP, JUMPZ, SET, GET.

### Leros

* https://github.com/leros-dev/leros

> An FPGA-optimized tiny processor core for utility functions (e.g., SW UART). The challenge is to get the resources below 500 LC and use just 2 RAM blocks. The initial 16-bit version in VHDL and supported by a small Java runtime (muvium). The redesign of 16/32/64-bit version in Chisel is supported by a C compiler (LLVM port). 21 instructions. LC count of Leros is slightly higher than the one of PicoBlaze. 16-bit Leros consumes less than 200 logic cells and 1–2 on-chip memories.

### Lipsi

* https://github.com/schoeberl/lipsi

> Lipsi is probably the smallest processor around to enable implementing classic finite state machine logic in software without overhead. LE count of Lipsi is slightly lower than the one of PicoBlaze, around 100 LEs and one block RAM. Lipsi is written in Chisel. Lipsi is an 8-bit processor organized as an accumulator machine. Instructions: st, brl, ldind, stind, br, brz, brnz, sh, io, exit. Immediate and register instructions: add, sub, adc, sbb, and, or, xor, ld.

### howerj subleq-vhdl

* https://github.com/howerj/subleq-vhdl

> 16-bit SUBLEQ computer written in VHDL for an FPGA written in VHDL that runs eForth. Synthesized for a Spartan-6: 36 slices, 124 LUTs.

### MT15

* http://www.6502.org/users/dieter/mt15/mt15.htm

> MT15 is a (mostly) transistorised CPU. 74xx chips are used in three places: 74LS164/74LS27 is used to generate the 4_phase_clock, instruction decoder outputs are buffered with four 74HCT245, and another four 74HCT245 work as buffer for the 16 bit address and data bus. Circa 3000 low frequency BC847/BC857 SMD transistors, 3 EuroCents each.

## From TTL IC

### Crazy Small CPU version 2

* https://github.com/DoctorWkt/CSCv2
* https://minnie.tuhs.org/Programs/CrazySmallCPU/

> The Verilog directory holds an implementation of the CPU in Icarus Verilog. The ALU can perform sixteen operations, some with carry: decimal add, decimal subtract, and, or, xor, increment, set flags, zero, add, subtract, select, multiply, divide, remainder. One RAM chip, one ROM chip that acts as an ALU, two ROM chips that provide the control logic, three registers, two counters, one multiplexer and one timer for a total of eleven chips.

### DIY Computer

* http://www.wellytop.com/Fnagaton/DIYComputer.html

> Or Yet Another DIY Processor Using TTL

### Gigatron TTL

* https://hackaday.com/2019/03/25/how-the-gigatron-ttl-microcomputer-works/
* https://gigatron.io/

> HOW THE GIGATRON TTL MICROCOMPUTER WORKS
> doesn’t even contain the 74181 ALU-in-a-chip. 36 TTL chips, a RAM, and a ROM. RISC architecture

### Homebuilt 8080 Mk II

* https://lovqvist.net/8080-1/homebuilt-8080-mk-ii/

> 74HC logic. 72 instruction variants. Will be parallel microcoded (the only part using IC, 32Kx8 SRAM.

### Nibbler

* https://www.bigmessowires.com/nibbler/
* https://github.com/bchangip/NibblerCPU
* https://gist.github.com/erincandescent/347577465129882abc97

> Nibbler is a 4 bit CPU built from standard 7400 series logic chips – individual counters, registers, buffers, and gates. It’s an educational example of a simple CPU that’s easy to understand and build, but still capable of running games and other interesting programs. Nibbler is built using wire-wrapping on a 5 x 4 inch (127 x 102 mm) perfboard. Thirteen 7400-series chips in the CPU data and control paths, two 28C16 EEPROMs store microcode for generating internal control signals, 4K x 4 SRAM, 28C64 EEPROM stores programs. 16 instructions: JMP, JC, JNC, JZ, JNZ, LD, ST, LIT, OUT, IN, ADDI, ADDM, CMPI, CMPM, NORI, NORM.

### Novasaur CP/M

* https://hackaday.io/project/164212-novasaur-cpm-ttl-retrocomputer

> Novasaur CP/M TTL Retrocomputer: Retrocomputer built from TTL logic running CP/M with no CPU or ALU

* https://hackaday.com/2020/12/11/surfing-the-web-with-7400-logic/

> SURFING THE WEB WITH 7400 LOGIC

### Ben Eater 8-bit breadboard computer

* https://github.com/space1649/8-bit-SAP-Breadboard-Computer-by-Space-Man

## From transistors

### FullTr-11

* http://recursion.jp/comp/e/

> Total number of parts: 6926. Both 11-bit CPU and memory are made only of discrete transistors. Clock: 1 KHz, registers: A, B and C, RAM: 5.5 bytes, ROM: 128 bytes. Opcode length is 5-bit. Since the opcode is prepended to the 11-bit operand, the total length of instruction is 16 bit. Instructions: MOV, ADD, SUB, JMP, JNC.

### Megaprocessor

* https://www.megaprocessor.com/boards.html

> There are four general purpose 16 bit registers: R0, R1, R2, R3. There is a program counter, PC. A register dedicated as the stack pointer SP. And a processor status register, PS. For computation there is a 16 bit ALU and a 16 bit adder. 8-bit opcodes with up to two bytes of following immediate data. 16-bit address, about 20kHz clock, 256 bytes RAM, 256 bytes PROM, 8500 LEDs for CPU, 2048 for RAM. 50500 resistors, 15300 transistors for CPU, 27000 for RAM. A fair proportion of these are used to drive the LEDs (pretty much one for one).

### Monster 6502

Table sized CPU that would be plausible to both review and construct at home:

* https://monster6502.com/
* https://news.ycombinator.com/item?id=11703596

### Manufacturing IC

Manufacturing integrated circuits at home (not recommended):

* https://www.electronicsforu.com/technology-trends/printed-integrated-circuits-that-consist-of-several-hundred-transistors
* http://sam.zeloof.xyz/

## Relay

### Harry Porter 2006

* 415 four pole, double throw relays, 111 switches, 350 LED
* 8-24 cycles per instruction
* 16-bit address: PC
* 8-bit registers: A, B, C, D, indirect (X & Y, M1 & M2), flags (Z, Cy, S)
* 32KB SRAM

Instructions:
* add, inc, and, or, xor, not, shl, nop
* load signed 5-bit immediate, load 16-bit immediate, clear
* 8-bit and 16-bit move, 16-bit increment, load, store
* goto, call, branch indirect, branch if negative, branch if carry, branch if zero, branch if not zero
* halt

References:
* https://web.cecs.pdx.edu/~harry/Relay/RelayPaper.htm
* https://web.cecs.pdx.edu/~harry/Relay/
* https://meatfighter.com/tofu/harryporter/index.html
* https://jenda.hrach.eu/f2/RelayTalk.pdf
* https://www.relaycomputer.co.uk/pages/overview/

### Jon Stanley 2007

* 168 SPDT relay, 100 4PDT relay, 13 other relays, 26 switches, 100 LED
* 2kB SRAM
* 8-bit registers: A, B, C

Instructions:
* load immediate, load, store, move
* A+B, A and B, not A, increment, nop
* shift right, shift left
* branch, branch if (not) positive/zero/negative
* halt

References:
* https://www.electronixandmore.com/projects/relaycomputertwo/index.html

### Daniel Fremont 2009

* 200 four pole, double throw relays
* 9-12 cycles per instruction
* 16-bit address: PC
* 8-bit registers: A, B, result (C), indirect (X & Y), flags (Z, Cy, S)
* 32KB SRAM

Instructions:
* lda, ldb, ldia, ldib, ldx, ldy
* stic
* ctx, cty
* add, and, or, nota, notb, xor, xnor, atc, btc
* goto, braz, bran, brac
* lsh

References:
* https://asr.menloschool.org/wp-content/uploads/2022/01/d9030-computer_daniel.pdf

## Storage

Read-only:

* https://en.wikipedia.org/wiki/Serinette
* https://en.wikipedia.org/wiki/Barrel_organ#Barrel
* https://en.wikipedia.org/wiki/Music_box
* https://en.wikipedia.org/wiki/Jacquard_machine#Principles_of_operation
* https://en.wikipedia.org/wiki/Music_roll
* https://en.wikipedia.org/wiki/Piano_roll
* https://en.wikipedia.org/wiki/Book_music
* https://en.wikipedia.org/wiki/Core_rope_memory

Write-once, read-multiple:

* https://en.wikipedia.org/wiki/Punched_tape
* https://en.wikipedia.org/wiki/Punched_card

Read-write:

* https://en.wikipedia.org/wiki/Drum_memory
* https://en.wikipedia.org/wiki/Magnetic-core_memory

## Historical

### Librascope LGP-21

* https://en.wikipedia.org/wiki/LGP-30#LGP-21
* https://www.e-basteln.de/computing/lgp21/lgp21/

> LGP-21 had about 460 transistors and about 375 diodes

### Calculators

* https://en.wikipedia.org/wiki/Mechanical_computer
* https://en.wikipedia.org/wiki/Analog_computer

## From raw materials

### Ridel mechanical Turing machine in wood

* https://hackaday.com/2018/03/08/mechanical-wooden-turing-machine/
* https://gwern.net/doc/cs/hardware/2017-ridel.pdf

### Jim MacArthur Turing machine

* https://github.com/jmacarthur/millihertz/tree/master/scad/newbuild/
* https://hackaday.com/2011/03/25/mechanical-turing-machine-can-compute-anything-slowly/
* https://srimech.blogspot.com/2011/03/turing-machine-and-maker-faire.html
* https://www.srimech.com/Mechanical%20Turing%20Machine.html

## References

* https://www.homebrewcpuring.org/
