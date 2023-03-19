# Wave a flag

## Objetivo

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information...

## Solución

Es necesario descargar el archivo anexo.
Enseguida...

```bash
hone@Unidad03:~$ cd Descargas/
```

```
hone@Unidad03:~/Descargas$ chmod +x warm
```

```
hone@Unidad03:~/Descargas$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
```

Bandera: *picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}*

## Referencias
