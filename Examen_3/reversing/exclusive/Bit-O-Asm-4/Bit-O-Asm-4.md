# Bit-O-Asm-4

## Objetivo

Can you figure out what is in the eax register? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Solución

Se descarga el siguiente codigo en ensambladro

```bash
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
```

Al inicio se almacena en la pila[rbp-0x4] el valor de 0x9fe1a;

Se compara el valor de pila[rbp-0x4], si es menor o igual que 0x2710. No es asi, por lo que se continua.

se resta de pila[rbp-0x4] el valor 0x65.

Se salta hasta la linea 41.

El valor pila[rbp-0x4] se almacena en eax

El valor almacenado es 654773 en decimal. Es este numero se forma la bandera.

Bandera: *picoCTF{654773}*

## Referencias

[Las instrucciones del ensamblador](https://moisesrbb.tripod.com/unidad5.htm)
