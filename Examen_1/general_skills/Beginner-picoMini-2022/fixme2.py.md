# fixme2.py

## Objetivo

Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/66/fixme2.py)

## Solución

Es necasario descargar el archivo adjunto. Despues...

```bash
hone@Unidad03:~/Descargas$ nano fixme2.py 
```

y se muestra el siguiente codigo:

```python

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) + chr(0x5f) + chr(0x1f) + chr(0x10) + chr(0x3b) + chr(0x1b) + chr(0x55) + chr(0x1a) + chr(0x34) + chr(0x5d) + chr(0x51) + chr(0x40) + chr(0x54) + chr(0x09) + chr(0x05) + chr(0x04) + chr(0x57) + chr(0x1b) + chr(0x11) + chr(0x31) + chr(0x5f) + chr(0x51) + chr(0x52) + chr(0x46) + chr(0x00) + chr(0x5f) + chr(0x5a) + chr(0x0b) + chr(0x19)

flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag = "":
 print('String XOR encountered a problem, quitting.')
else:
 print('That is correct! Here\'s your flag: ' + flag)
```

al obseservarlo, podemos notar que existe unproblema en la linea:

```python
if flag = "":
```

Es necesario cambiar esa asignacion con una comparacion, quedando de la siguiente manera.

```python

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) + chr(0x5f) + chr(0x1f) + chr(0x10) + chr(0x3b) + chr(0x1b) + chr(0x55) + chr(0x1a) + chr(0x34) + chr(0x5d) + chr(0x51) + chr(0x40) + chr(0x54) + chr(0x09) + chr(0x05) + chr(0x04) + chr(0x57) + chr(0x1b) + chr(0x11) + chr(0x31) + chr(0x5f) + chr(0x51) + chr(0x52) + chr(0x46) + chr(0x00) + chr(0x5f) + chr(0x5a) + chr(0x0b) + chr(0x19)

flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
 print('String XOR encountered a problem, quitting.')
else:
 print('That is correct! Here\'s your flag: ' + flag)
```

```bash
hone@Unidad03:~/Descargas$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

Bandera: *picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}*

## Referencias
