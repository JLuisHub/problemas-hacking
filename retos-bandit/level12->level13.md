# Level 12 -> level 13

## Objetivo

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit12**

Password: **JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv**

## Solución

```bash
hone@Unidad03:~$ ssh bandit12@bandit.labs.overthewire.org -p 2220
```

```bash
bandit12@bandit.labs.overthewire.org's password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM 
```

```bash
bandit12@bandit:~$ mkdir /tmp/newdir
```

```bash
bandit12@bandit:~$ ls
data.txt
```

```bash
bandit12@bandit:~$ cp data.txt /tmp/newdir
```

```bash
bandit12@bandit:~$ cd /tmp/newdir
```

```bash
bandit12@bandit:/tmp/newdir$ cat data.txt | xxd -r | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix
```

```bash
bandit12@bandit:/tmp/newdir$ xxd -r data.txt | zcat | bzcat | gzip -d | tar xO | tar xO | bzip2 -d | tar xO | gzip -d | cat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```


## Notas adicionales

## Referencias

[Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)
