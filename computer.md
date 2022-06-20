### DeMorgan's Law:   
not (A or B) = (not A) and (not B).   
not (A and B) = (not A) or (not B).  

### Boolean Logic:
Any boolean operation can be constructed by using only the NAND gate.      
NAND(x,x) = NOT(x). 
XOR(x,y) = 1 when number of true inputs is odd.    
Can also be represented as |a-b|.    
The XOR logic gate can be used as a one-bit adder that adds any two bits together to output one bit.   

### Number conversion:  
A regular decimal number is the sum of the digits multiplied with power of 10.  
137 = 1×10^2+3×10^1+7×10^0 = 100+30+7.   
Hex numbers are read the same way, but each digit counts power of 16 instead of power of 10.   
3B = 3×16^1 + 11×16^0 = 48 + 11 = 59.    
3B = 00111011.   

#### Binary Numbers:    
If N bits, we can represent 2^N possibilities
With 1 Bit: 2 possibilities : 0 and 1.  
With 2 Bits: 4 possibilities: 00, 01 , 10, 11.  
With 3 Bits: 8 possibilities: 000,001,010,.....,111    
Binary to decimal:   $\sum {b_i} 2^i $.   
Decimal to Binary:  Keep on findind multiples of 2 and add them up until it becomes the target number.    
87 = 64+16+4+2+1 = 1010111.  

#### Negative Numbers in binary:
Two's complement represent a negative number using positive number: 2^n-x.   
For example, in 4 bit integers, -5 will be represented as 2^4 - 5 = 11.  This prevents issues with alternative implementations using MSB as sign.It will have -0 as one of the value.     
Addition in 2's complement is free.  
-2 + -3 ==> (16-2)+(16-3) = 14 + 13 = 1110+1101 = 1011 = -5 .   
Computing -x:   
complement = 2^n - x = 1+ (2^n -1) -x    
2^n-1 is always 1111..1 (n times) .111.11 - x is just flipping 0's and 1's.     
Finally, for adding 1, start from left flipping numbers until first 0 is found. Which can be flipped to 1 and rest remains same.   
-4 = 8-4 = 4 = 0100 = 1011+1 = 1100 (12).  

#### Bitwise Operators:  
 LEFT SHIFT: << :: makes numbers bigger by shifting their bits to higher places.  
 Eg: N<<i (N: first operand, i: second operand).  
 Takes two numbers, left shifts the bits of the first operand, the second operand decides the number of places to shift. Or in other words left shifting an integer “x” with an integer “y” denoted as ‘(x<<y)’ is equivalent to multiplying x with 2^y (2 raised to power y).    
Example 1: Shift 7 by 1 bit assuming 4 bit:  7=> 0111 << 1 => 1110 => 14 (dec).  
Example 2: Shift 1 by 3 bits = 0001 => 1000  
Example 2: Shift 1 by 7 bits = 00000001 => 10000000

### Bus:
Group of bits that are manipulated together is called as a bus.
### HDL:  Hardware Description Language.    
An HDL program consists of an interface and an implementation. The interface consists of the chip's API documentation, chip name, and names of its input and output pins. The implementation consists of the statements below the PARTS keyword.    

  CHIP Or {  
    IN a, b;  
    OUT out;  
  
    PARTS:  
	Nand(a=a,b=a,out=c);  
	Nand(a=b,b=b,out=d);  
	Nand(a=c,b=d,out=out);  
} 
  
#### Commonly used Gates:   
Elementary:   
- Not
- And
- Or
- Xor
- Mux
- Dmux  
16 Bit Variants:   
- Not16
- And16
- Or16
- Mux16  
Multi-Way variants:  
- Or8Way
- Mux4Way16
- Mux8Way16
- DMux4Way
- DMux8Way

#### Multiplexer (Mux) and Demultiplexer (DeMux) 
Multiplexer selects an input a or b depending on weather the selector pin in on or off.   
if (sel == 0), out = a else b.   
Can be implemented using And, Or and Not gates.  
    
A demultiplexer channels an input to a or b depending on weather the selector pin is on or off.The rest of the pins gets 0.   
if (sel == 0), a = 1 else b = 1.    
Inverse of multiplexer.   

#### Combinational Logic:
Combinational logic (also referred to as time-independent logic or combinatorial logic) is a type of digital logic which is implemented by Boolean circuits, where the output is a pure function of the present input only. Ex. ALU.     
out[t] = f(in[t])    
In Sequential logic, the output is dependent on input of previous time unit.   
out[t] = f(in[t-1])    

### Flip-Flops. 
In building memory circuits, the components have to remember one bit of information from time t-1, and at the end of time, can can toggle between two states: 0 or 1. Hence they are called Flip-Flops.A D flip flop can be made from NAND gates.   
A 1-bit register can remember an input but "forever", until requested to load a new value.   
Bit(in,load, out).  if load(t-1)==1:out[t] = in[t-1].   

#### Memory Registers:   
Array of 1-bit registers. The width is the number of registers in the array.   
A 16 bit computer has registers with 16bits.
RAM can be defined as sequence of n addressable registers, with addreessed of 0 to n-1.RAM is a sequential chip.     
At any given time, only 1 of the registers in RAM is selected. The number of bits in adress selection bus is therefore log n.
The number of input lines to the register is called the word width (w).Width is the amount of data a single register holds.   
To read RAM we set the address of the address of the selected register. The out of the RAM unit emits state of the selected register.This is how we read one out of millions of registers.  
Irrespective of RAM size, every register can be accessed at the same time!!

#### Counters:  
Used to keep track of which instruction should be fetched and executed next.
This control mechanism is realized by Program Counter.    
The counter supports three primitive operations: Reset, Next, GoTo. 


#### CPU Registers.  
CPU contains a few, fast registers. Their number and functions are central part of the machine language.   
Data Registers: Used for storing data, like ints and floats.    
Address Registers:  Store address of main memory which operation wants to access.   
Store R1, @A1 : store contens of R1 into address specified by A.  
Addressing Modes:   
Register: Add R1, R2.  
Direct: Add R1, M[200]. 
Indirect: Add, @A
Immediate: Add 73, R1    

### Flow control:   
Most of the times, CPU executes the instructions sequentially.  
Unconditional Jump: Used to jump to another location, e.g in for loop. 

### PIC10F200 Microcontroller:   
- 33 single-word instructions, each instruction is 12 bit wide.
- example instruction: 0001 0000 0010
- 2 level deep hardware stack
- 8 bit wide data bus
- direct, indirect and relative addressing
- 8 special hardware registers
- 4MHZ internal clock
- 16bytes RAM

### PIC10F200 Microcontroller TRIS register:   

TRIS : 8 bit tri-state register to configure the corresponding bit as i/p or o/p.  
A 0 in the bit indicates o/p mode, 1 indicates i/p mode.    
The pin names in the data sheets are actually the names of port bits. The pins are typically grouped in 8 and have their corresponding registers.  
For example: RA0, RA1...RAx have TRISA.  

### PIC10F200 Microcontroller WREG register: 
The 8 bit WREG register is the most widely used register in the PIC micro-controllers. WREG stands for working register, as there is only one. The WREG register is the same as the accumulator in other microprocessors. The WREG register is used for all arithmetic and logic instructions.    

### PIC10F200 Microcontroller file register: 
The PIC microcontroller has many other registers in addition to the WREG register. They are called data memory space to distinguish them from program (code) memory space. The data memory space in PIC is a read/write (Static RAM) memory. In the PIC microcontroller literature, the data memory is also called the file register.     
The Special Function Register (SFRs) are dedicated to specific functions such as ALU status, timers, serial communication, I/O ports, ADC and so on.  
The general purpose registers are a group of RAM locations in the file register that are used for data storage and scratch pad. Each location is 8 bits wide and can be used to store any data we want as long as it is 8 bit. 


### PIC10F200 Microcontroller assembly commands:
MOVLW 05h ## Move Literal to Working Register   
MOVWF 010h ## Move value to file register.  
ADDWF 10h, 1 ## add the value in WREG with 10h and store the value in 10h register.
DECFSZ 010h,F  ## Decrement f, Skip if 0. If the second operand is F, then the result of the decrement is stored back to the file register, and if the second operator is W then the result is stored to the W register.      
CLRF 010h; Clear file register.     
SUBWF: SUBtract W from File register.   


### PIC10F200 Microcontroller assembly sample:
#include <xc.inc>     
    
CONFIG WDTE = OFF  ; Watchdog Timer (WDT disabled).   
; WDT restarts the main controller if it is hanged.   
CONFIG CP = OFF    ; Code Protect (Code protection off).   
CONFIG MCLRE = OFF ; Master Clear Enable (MCLR disabled, GP3 enabled).   
    
PSECT MyCode,class=CODE,delta=2   
i EQU 13h   
; Constants “i” is set t0 0x10. This gives names to specific unnamed general purpose register.  
; It’s difficult to remember what is stored in register 0x10 if the program is big,   
; but, by this directive, we know that 0x10 is called “i”   

INIT:   
    MOVLW 2h; Move 2h to Working Register.   
    MOVWF 10h; Move 2 to register 10h (register number 16).   
    ; Resigter 10h => 00000010 (2).   
    MOVLW 5h; Move 5h to Working Register.   
    ADDWF 10h, 1; Add contents of WREG to contents at 10h and store it back on register 10h     
    ; Resigter 10h => 00000111 (7).   
    MOVLW 1h<<2; Shift 1 by 2 bits and store it in WREG; 00000100.   
    MOVWF 11h; Store the shifted contents back on register at 11h.   
    ; Resigter 11h : 00000100.   
    BCF 11h, 2  ; Set 3rd bit (starts with 0) of register to 0    
    ; Resigter 11h : 00000000    
    MOVLW 3h<<2; Shift 3h(00000011) by 2 => 00001100 => 12.   
    MOVWF i; Store 12 into register at 13h.   
    ; Resigter 13h : 00001100.   
    TRIS GPIO; set the contents of TRIS register as 00001100.   
    BSF 15h, 2  ; Set 3rd bit (starts with 0) of register to 1.   
    ; Resigter 15h : 00000100    
 
Loop:    ; Loop until contents of 13h becomes zero, i.e 13 times.   
    NOP 
    DECFSZ i,F     
    GOTO Loop     
    
    MOVLW 10h; Store 10h at register 14h.   
    MOVWF 14h;   
    END INIT;       









