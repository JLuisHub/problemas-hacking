# reverse_cipher

## Objetivo

We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

## Solución

```bash
hone@unidad03:~/reverse_cipher$ objdump -D rev -M intel | grep '<main>:' -A50
0000000000001185 <main>:
    1185:	55                   	push   rbp
    1186:	48 89 e5             	mov    rbp,rsp
    1189:	48 83 ec 50          	sub    rsp,0x50
    118d:	48 8d 35 74 0e 00 00 	lea    rsi,[rip+0xe74]        # 2008 <_IO_stdin_used+0x8>
    1194:	48 8d 3d 6f 0e 00 00 	lea    rdi,[rip+0xe6f]        # 200a <_IO_stdin_used+0xa>
    119b:	e8 d0 fe ff ff       	call   1070 <fopen@plt>
    11a0:	48 89 45 e8          	mov    QWORD PTR [rbp-0x18],rax
    11a4:	48 8d 35 68 0e 00 00 	lea    rsi,[rip+0xe68]        # 2013 <_IO_stdin_used+0x13>
    11ab:	48 8d 3d 63 0e 00 00 	lea    rdi,[rip+0xe63]        # 2015 <_IO_stdin_used+0x15>
    11b2:	e8 b9 fe ff ff       	call   1070 <fopen@plt>
    11b7:	48 89 45 e0          	mov    QWORD PTR [rbp-0x20],rax
    11bb:	48 83 7d e8 00       	cmp    QWORD PTR [rbp-0x18],0x0
    11c0:	75 0c                	jne    11ce <main+0x49>
    11c2:	48 8d 3d 57 0e 00 00 	lea    rdi,[rip+0xe57]        # 2020 <_IO_stdin_used+0x20>
    11c9:	e8 62 fe ff ff       	call   1030 <puts@plt>
    11ce:	48 83 7d e0 00       	cmp    QWORD PTR [rbp-0x20],0x0
    11d3:	75 0c                	jne    11e1 <main+0x5c>
    11d5:	48 8d 3d 7e 0e 00 00 	lea    rdi,[rip+0xe7e]        # 205a <_IO_stdin_used+0x5a>
    11dc:	e8 4f fe ff ff       	call   1030 <puts@plt>
    11e1:	48 8b 55 e8          	mov    rdx,QWORD PTR [rbp-0x18]
    11e5:	48 8d 45 b0          	lea    rax,[rbp-0x50]
    11e9:	48 89 d1             	mov    rcx,rdx
    11ec:	ba 01 00 00 00       	mov    edx,0x1
    11f1:	be 18 00 00 00       	mov    esi,0x18
    11f6:	48 89 c7             	mov    rdi,rax
    11f9:	e8 42 fe ff ff       	call   1040 <fread@plt>
    11fe:	89 45 dc             	mov    DWORD PTR [rbp-0x24],eax
    1201:	83 7d dc 00          	cmp    DWORD PTR [rbp-0x24],0x0
    1205:	7f 0a                	jg     1211 <main+0x8c>
    1207:	bf 00 00 00 00       	mov    edi,0x0
    120c:	e8 6f fe ff ff       	call   1080 <exit@plt>
    1211:	c7 45 f8 00 00 00 00 	mov    DWORD PTR [rbp-0x8],0x0
    1218:	eb 23                	jmp    123d <main+0xb8>
    121a:	8b 45 f8             	mov    eax,DWORD PTR [rbp-0x8]
    121d:	48 98                	cdqe   
    121f:	0f b6 44 05 b0       	movzx  eax,BYTE PTR [rbp+rax*1-0x50]
    1224:	88 45 ff             	mov    BYTE PTR [rbp-0x1],al
    1227:	0f be 45 ff          	movsx  eax,BYTE PTR [rbp-0x1]
    122b:	48 8b 55 e0          	mov    rdx,QWORD PTR [rbp-0x20]
    122f:	48 89 d6             	mov    rsi,rdx
    1232:	89 c7                	mov    edi,eax
    1234:	e8 27 fe ff ff       	call   1060 <fputc@plt>
    1239:	83 45 f8 01          	add    DWORD PTR [rbp-0x8],0x1
    123d:	83 7d f8 07          	cmp    DWORD PTR [rbp-0x8],0x7
    1241:	7e d7                	jle    121a <main+0x95>
    1243:	c7 45 f4 08 00 00 00 	mov    DWORD PTR [rbp-0xc],0x8
    124a:	eb 43                	jmp    128f <main+0x10a>
    124c:	8b 45 f4             	mov    eax,DWORD PTR [rbp-0xc]
    124f:	48 98                	cdqe   
    1251:	0f b6 44 05 b0       	movzx  eax,BYTE PTR [rbp+rax*1-0x50]
```

Con el programa ghidra se abre el binario para analizar, se muestra la funcion **main**.

![img1](img1.png)

Se muestra codigo en lenguaje c, y se realiza codigo en python para realizar un inverson de la siguiente secion.

![img2](img2.png)

```python
desorganizada = "picoCTF{w1{1wq8/7376j.:}"

flag = desorganizada[:8]

for i in range(8, len(desorganizada)):
    if i & 1 == 0:
        flag += chr( ord(desorganizada[i]) -5)
    else:
        flag += chr( ord( desorganizada[i] ) +2)

print(flag)

picoCTF{r3v3rs312528e05
```

Bandera: *picoCTF{r3v3rs312528e05}*

## Referencias
