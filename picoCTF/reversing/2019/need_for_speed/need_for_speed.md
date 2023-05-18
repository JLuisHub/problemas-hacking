# Need For Speed

## Objetivo

The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

## Solución

```bash
hone@unidad03:~/need_for_speed$ gdb need-for-speed 
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
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb)
```

```
(gdb) set disassembly-flavor intel
```

```
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:	push   rbp
   0x000000000000091b <+1>:	mov    rbp,rsp
   0x000000000000091e <+4>:	sub    rsp,0x10
   0x0000000000000922 <+8>:	mov    DWORD PTR [rbp-0x4],edi
   0x0000000000000925 <+11>:	mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000000929 <+15>:	mov    eax,0x0
   0x000000000000092e <+20>:	call   0x8d8 <header>
   0x0000000000000933 <+25>:	mov    eax,0x0
   0x0000000000000938 <+30>:	call   0x82f <set_timer>
   0x000000000000093d <+35>:	mov    eax,0x0
   0x0000000000000942 <+40>:	call   0x87d <get_key>
   0x0000000000000947 <+45>:	mov    eax,0x0
   0x000000000000094c <+50>:	call   0x8ac <print_flag>
   0x0000000000000951 <+55>:	mov    eax,0x0
   0x0000000000000956 <+60>:	leave  
   0x0000000000000957 <+61>:	ret    
End of assembler dump.
```

```
(gdb) break main
Breakpoint 1 at 0x91e
```

```
(gdb) run
Starting program: /need-for-speed 

Breakpoint 1, 0x000055555540091e in main ()
```


```
(gdb) run
The program being debugged has been started already.
Start it from the beginning? (y or n) y
Starting program: /home/hone/Documentos/Materias/Seguridad_Redes_Sistemas/problemas-hacking/picoCTF/reversing/2019/need_for_speed/need-for-speed 

Breakpoint 1, 0x000055555540091e in main ()
```

```
(gdb) call (int) get_key()
Creating key...
Finished
$1 = 9
```

```
(gdb) call (int) print_flag()
Printing flag:
PICOCTF{Good job keeping bus #190ca38b speeding along!}
$2 = 56
```

Bandera: *PICOCTF{Good job keeping bus #190ca38b speeding along!}*

## Referencias

[GDB: The GNU Project Debugger](https://www.sourceware.org/gdb/)
