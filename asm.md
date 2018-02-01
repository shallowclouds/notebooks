```bash
# compile *.asm to *.o
$ nasm -f elf64 first.asm -o first.o
# link *.o to excutable file.
$ gcc -m64 first.o -o first
# in x64 platform.

