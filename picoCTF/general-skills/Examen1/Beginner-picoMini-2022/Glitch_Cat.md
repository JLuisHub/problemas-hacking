# Glitch Cat

## Objetivo

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 65353`

## Solución

```bash
hone@Unidad03:~$ nc saturn.picoctf.net 65353
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
```

Se convierte de hexadecimal a texto con python y se obtiene el resto de la bandera.

```bash
one@Unidad03:~$ python3
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64))
9c42a45d
```

```
picoCTF{gl17ch_m3_n07_9c42a45d}
```

Bandera: *picoCTF{gl17ch_m3_n07_9c42a45d}*

## Referencias
