# Embeeded
.globl _start

_start:
    li sp, 0x80001000
    jal function
    j .

int function() 
{
    return 42;
}

riscv64-unknown-elf-gcc -O0 -ggdb -nostdlib -march=rv32i -mabi=ilp32 -Wl,-Tm.ld m.s c-asm.c -o main.elf
