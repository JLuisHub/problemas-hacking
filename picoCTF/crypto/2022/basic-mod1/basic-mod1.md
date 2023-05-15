# basic-mod1

## Objetivo

We found this weird message being passed around on the servers, we think we have a working decryption scheme.

Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).

Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.

Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

## Solución

```bash
hone@unidad03:~/basic-mod1$ cat message.txt 
350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213
```

```
350 mod 37 = 17 --> R
63 mod 37 = 26 -26 --> 0
353 mod 37 = 20 --> U
198 mod 37 = 13 --> N
114 mod 37 = 3 --> D
369 mod 37 = 36 --> _
346 mod 37 = 13 --> N
184 mod 37 = 36 --> _
202 mod 37 = 17 --> R
322 mod 37 = 26 -26 --> 0
94 mod 37 = 20 --> U
235 mod 37 = 13 --> N
114 mod 37 = 3 --> D
110 mod 37 = 36 --> _
185 mod 37 = 0 --> A
188 mod 37 = 3 --> D
225 mod 37 = 3 --> D
212 mod 37 = 27 -26 --> 1
366 mod 37 = 33 -26 --> 7
374 mod 37 = 4 --> E
261 mod 37 = 2 --> C
213 mod 37 = 28 -26 --> 2
```

Bandera: *picoCTF{R0UND_N_R0UND_ADD17EC2}*

## Referencias
