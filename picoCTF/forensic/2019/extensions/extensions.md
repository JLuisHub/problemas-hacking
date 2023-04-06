# extensions

## Objetivo

This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Solución

```bash
hone@Unidad03:~/extensions$ file flag.txt 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
```

Nos damos cuenta que en realidad es una imagen, no un archivo txt, asi que lo que hacemos es abrirla como imagen.

```bash
hone@Unidad03:~/extensions$ mv flag.txt flag.png
```

```bash
hone@Unidad03:~/extensions$ open flag.png
```

Se abre la siguiente imagen con la bandera.

![img-bandera](flag.png)

Bandera: *picoCTF{now_you_know_about_extensions}*

## Referencias
