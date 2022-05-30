
### Pointers
In Present day compilers every pointer takes 8 bytes.   
A program can only access code section or the stack section of memory. But with pointers, it can keep the address in stack and refer to heap section of the memory.

### Pointers: declartion, initialised and dereferencing
int x=10; is a data variable.   
int *p=&x; p is a pointer and will be pointing on x. p is declared and initialised.   
int y = *p;    
float *p2;    
struct Test *p5;   
