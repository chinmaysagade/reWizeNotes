
### Pointers
In Present day compilers every pointer takes 8 bytes.   
A program can only access code section or the stack section of memory. But with pointers, it can keep the address in stack and refer to heap section of the memory. That is the reason you can only do system programming using C/C++ since other programming languages do not allow accessing heap section of the memory directly.

### Pointers: declartion, initialised and dereferencing
int x=10; is a data variable.   
int *p=&x; p is a pointer and will be pointing on x. p is declared and initialised.   
int y = *p;    
float *p2;    
struct Test *p5;   

### Pointers: Stack vs Heap
Dynamic memory is created in Heap using pointers.   
Heap memory can be accessed from anywhere in the program, if its address is available.   
int A[5] = {0} --- Will be created on stack !   
int *h;
int *h = new int[5]; -- with new, array is created in heap. Since its in heap, you need to collect it in pointer.   
Heap memoery is avaiable throughout the time the program is running. Hence if it's not needed after sone time, heap should be deleted.

### Strings
char s[20]: //can store 19 characters. Last will be string delimiter \0
char x = 'A';  
char s1[10] = "Hello";  
char s2[] = "hello";   // Will be created in stack. 
char s3[]={'h','e','l','l','\0'}; // will not be a string unless string delimiter \0 is declared. 
char *S = "Hello";  // Will be created in heap. warning: ISO C++11 does not allow conversion from string literal to 'char *'.   
std::string s = "hello";    
cin.getline(s, 20) ; //Read 20 characters from keyboard to string s
