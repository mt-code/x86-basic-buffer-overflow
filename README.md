# x86 Basic Buffer Overflow
Exploits an unsafe strcpy call to achieve a shell by exploiting a buffer overflow.

### Preparation

Ensure ASLR is disabled so the memory addresses are not randomised:

`echo 0 > /proc/sys/kernel/randomize_va_space`

Compile the vulnerable source with various buffer overflow protections disabled:

`gcc -m32 -g -fno-stack-protector -z execstack -o overflow overflow.c`

* **-m32**: Compiles as a 32-bit binary
* **-g**: Adds symbols for easier debugging

### Running the exploit

Simple call the vulnerable binary using our exploit output:

`./overflow $(./exploit.py)`