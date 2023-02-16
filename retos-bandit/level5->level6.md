# Level 5 -> level 6

## Objetivo
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit5**
Password: **lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR**

## Solución
```bash
hone@Unidad03:~$ ssh bandit5@bandit.labs.overthewire.org -p 2220
```

```
bandit4@bandit.labs.overthewire.org's password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

```bash
bandit5@bandit.labs.overthewire.org's password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

```bash
bandit5@bandit:~$ ls
inhere
```

```bash
bandit5@bandit:~$** cd inhere/
```

```bash
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
```

```bash
bandit5@bandit:~/inhere$ file maybehere{00..19}/* | find -size 1033c
./maybehere07/.file2
```

```bash
bandit5@bandit:~/inhere$ cat maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

## Notas adicionales
## Referencias