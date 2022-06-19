### DeMorgan's Law:   
not (A or B) = (not A) and (not B).   
not (A and B) = (not A) or (not B).  

### Boolean Logic:
Any boolean operation can be constructed by using only the NAND gate.      
NAND(x,x) = NOT(x). 
XOR(x,y) = 1 when number of true inputs is odd.    
Can also be represented as |a-b|.    
The XOR logic gate can be used as a one-bit adder that adds any two bits together to output one bit.   


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








