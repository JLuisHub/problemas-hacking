# transposition-trial

## Objetivo

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.
Download the corrupted message [here](https://artifacts.picoctf.net/c/192/message.txt).

## Solución

```bash
hone@unidad03:~/Documentos/Materias/Seguridad_Redes_Sistemas/problemas-hacking/Examen_3/crypto/2022/transposition-trial$ cat message.txt 
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2
```

Se crea un programa en python para reacomodar los caracteres de tal manera que creando grupos de tres, el tercer caracter de esos grupos de coloca al principio.

```python
revuelto = str('heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2')

bandera = ''
tercia = ''

for i in range(0,len(revuelto)):
    if( ( (i+1) % 3)==0 ):
        tercia = revuelto[i] + tercia
        bandera = bandera + tercia
        tercia = ""
    else:
        tercia = tercia + revuelto[i]

print(bandera)
```

```
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}
```

Bandera: *picoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}*

## Referencias
