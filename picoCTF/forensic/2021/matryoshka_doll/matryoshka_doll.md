# Matryoshka doll

## Objetivo

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)

## Solución

Se descarga la imagen con el link adjunto. Despues...

```bash
hone@unidad03:~/matryoshka_doll$ ls
dolls.jpg
```

```bash
hone@unidad03:~/Documentos/Materias/Seguridad_Redes_Sistemas/problemas-hacking/picoCTF/forensic/2021/matryoshka_doll$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378950, uncompressed size: 383938, name: base_images/2_c.jpg
651608        0x9F158         End of Zip archive, footer length: 22
```

```bash
hone@unidad03:~/matryoshka_doll$ ls
dolls.jpg  _dolls.jpg.extracted
```

```bash
hone@unidad03:~/matryoshka_doll$ cd _dolls.jpg.extracted/
```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted$ cd base_images/
```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted/base_images$ binwalk -e 2_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted/base_images$ cd _2_c.jpg.extracted/
```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ cd base_images/
```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ binwalk -e 3_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77651, uncompressed size: 79809, name: base_images/4_c.jpg
201423        0x312CF         End of Zip archive, footer length: 22

```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ cd _4_c.jpg.extracted/
```

```bash
hone@unidad03:~/matryoshka_doll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$ cat flag.txt
picoCTF{4f11048e83ffc7d342a15bd2309b47de}
```

Bandera: *picoCTF{4f11048e83ffc7d342a15bd2309b47de}*

## Referencias
