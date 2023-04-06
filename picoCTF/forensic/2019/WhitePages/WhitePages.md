# WhitePages

## Objetivo

I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

## Solución

Se descarga el archivo adjunto.

Despues de usar el siguiente [programa](program.py) escrito en python3

sed 's/ /0g'  whitepages.txt

```python
from pwn import *

archivo = open('whitepages.txt','rb')
data = bytearray(archivo.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)
```

```bash
hone@Unidad03:/WhitePages$ python3 program.py 
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'
```

Se puede obtener la bandera.

Bandera: *picoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}*

## Referencias
