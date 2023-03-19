# strings it

## Objetivo

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

## Solución

Es necesario descargar el archivo y moverse al directorio donde se encuetre.

```bash
hone@Unidad03:~$ cd Descargas/
```

Enseguida...

```bash
hone@Unidad03:~/Descargas$ strings ./strings | grep picoCTF{
picoCTF{5tRIng5_1T_7f766a23}
```

Bandera: *picoCTF{5tRIng5_1T_7f766a23}*

## Referencias

<https://linux.die.net/man/1/strings>
