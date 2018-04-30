```bash
# compile *.asm to *.o
$ nasm -f elf64 first.asm -o first.o
# link *.o to excutable file.
$ gcc -m64 first.o -o first
# in x64 platform.
```

`$?` 保存着上一个运行程序的返回值。

通用寄存器：`eax` 、`ebx` 、`ecx` 、`edx`

特殊寄存器：`esi` 、`edi` 、`ebp`

eax用于存放函数返回值

```bash
$ (gdb) set disassembly-flavor intel
$ (gdb) disas main
```

