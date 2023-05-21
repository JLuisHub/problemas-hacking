# Nombre

## Objetivo

Can you figure out what is in the eax register at the end of the main function? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

## Solución

```bash
one@unidad03:~/GDB_baby_step_2$ gdb debugger0_b 
GNU gdb (Debian 10.1-1.7) 10.1.90.20210103-git
Copyright (C) 2021 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
(gdb) set disassembly-flavor intel
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:	endbr64 
   0x000000000040110a <+4>:	push   rbp
   0x000000000040110b <+5>:	mov    rbp,rsp
   0x000000000040110e <+8>:	mov    DWORD PTR [rbp-0x14],edi
   0x0000000000401111 <+11>:	mov    QWORD PTR [rbp-0x20],rsi
   0x0000000000401115 <+15>:	mov    DWORD PTR [rbp-0x4],0x1e0da
   0x000000000040111c <+22>:	mov    DWORD PTR [rbp-0xc],0x25f
   0x0000000000401123 <+29>:	mov    DWORD PTR [rbp-0x8],0x0
   0x000000000040112a <+36>:	jmp    0x401136 <main+48>
   0x000000000040112c <+38>:	mov    eax,DWORD PTR [rbp-0x8]
   0x000000000040112f <+41>:	add    DWORD PTR [rbp-0x4],eax
   0x0000000000401132 <+44>:	add    DWORD PTR [rbp-0x8],0x1
   0x0000000000401136 <+48>:	mov    eax,DWORD PTR [rbp-0x8]
   0x0000000000401139 <+51>:	cmp    eax,DWORD PTR [rbp-0xc]
   0x000000000040113c <+54>:	jl     0x40112c <main+38>
   0x000000000040113e <+56>:	mov    eax,DWORD PTR [rbp-0x4]
   0x0000000000401141 <+59>:	pop    rbp
   0x0000000000401142 <+60>:	ret    
End of assembler dump.
```

Se coloca en pila[rbp-0x4] el valor de 0x1e0da.

Se coloca en pila[rbp-0xc] el valor de 0x25f.

Se coloca en pila[rbp-0x8] el valor de 0x0.

Se coloca en eax el valor de pila[rbp-0x8].

Se comparan los valores de eax y pila[rbp-0xc]

Si no es asi, por lo que se creara un ciclo hasta que sean iguales.

Al terminar se coloca en eax el valor de pila[rbp-0x4]

El valor en decimal es 307019, con este se forma la bandera

Bandera: *picoCTF{307019}*

## Referencias

[Las instrucciones del ensamblador](https://moisesrbb.tripod.com/unidad5.htm)
