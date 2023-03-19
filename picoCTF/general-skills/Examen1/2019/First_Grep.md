# First Grep

## Objetivo

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Solución

Es necesario descargar el archivo y moverse al directorio donde se encuetre.

```bash
hone@Unidad03:~$ cd Descargas/
```

Ensegida...

```bash
hone@Unidad03:~/Descargas$ cat file | grep picoCTF{
picoCTF{grep_is_good_to_find_things_5af9d829}
```

Bandera: *picoCTF{grep_is_good_to_find_things_5af9d829}*

## Referencias

<https://ryanstutorials.net/linuxtutorial/grep.php>
