# Nombre

## Objetivo

How about some hide and seek heh?
Look at this image [here](https://artifacts.picoctf.net/c/239/atbash.jpg).

## Solución

```bash
hone@unidad03:~/hidetosee$ steghide extract -sf atbash.jpg
Anotar salvoconducto: 
anot� los datos extra�dos e/"encrypted.txt".

```bash
hone@unidad03:~/hidetosee$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_1u84w779}
```

Se desencripta con el cifrado de Atbash para obtener la bandera.

Bandera: *picoCTF{atbash_crack_1f84d779}*

## Referencias
