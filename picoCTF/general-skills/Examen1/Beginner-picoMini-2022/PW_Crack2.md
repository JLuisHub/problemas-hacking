# PW Crack 2

## Objetivo

Can you crack the password to get the flag?
Download the password checker here and you'll need the encrypted flag in the same directory too.

## Solución

```bash
hone@Unidad03:~/Descargas$ python3 level2.py 
Please enter correct password for flag:
```

Podemos ver que es necesario una contraseña, para poder saber cual es, se necesita analizar el archivo.

```python
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
```

Convertimos la contraseña de hexadecimal a texto

```bash
hone@Unidad03:~/Descargas$ python3
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36))
de76
>>> exit()
```

```bash
hone@Unidad03:~/Descargas$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
```

Bandera: *picoCTF{tr45h_51ng1ng_489dea9a}*

## Referencias
