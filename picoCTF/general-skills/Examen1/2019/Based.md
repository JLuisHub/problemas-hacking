# Based

## Objetivo

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Solución

```bash
hone@Unidad03:~$ nc jupiter.challenges.picoctf.org 29956
```

Para solucionar este reto es necesario convertir los numeros en diferentes bases a texto-

```
Let us see how data is stored
lamp
Please give the 01101100 01100001 01101101 01110000 as a word.
...
you have 45 seconds.....

Input:
lamp
Please give me the  143 157 155 160 165 164 145 162 as a word.
Input:
computer
Please give me the 6d6170 as a word.
Input:
map
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}
```

En la primera, es necarios convertirlo de binario.
En segundo de octal.
y por ultimo de hexadecimal.

Bandera: *picoCTF{learning_about_converting_values_b375bb16}*

## Referencias
