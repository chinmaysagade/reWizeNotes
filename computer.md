### Boolean Logic:
Any boolean operation can be constructed by using only the NAND gate.      
NAND(x,x) = NOT(x). 
XOR(x,y) = 1 when number of true inputs is odd.    
Can also be represented as |a-b|.    
The XOR logic gate can be used as a one-bit adder that adds any two bits together to output one bit.   
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
- Not
- And
- Or
- Xor
- Mux
- Dmux
- Not16
- And16
- Or16
- Mux16
- Or8Way
- Mux4Way16
- Mux8Way16
- DMux4Way
- DMux8Way
