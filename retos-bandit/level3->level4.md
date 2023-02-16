# Level 3 -> level 4

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit3**
Password: **aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**

## Solución
```bash
hone@Unidad03:~$ ssh bandit3@bandit.labs.overthewire.org -p 2220
```

```
bandit3@bandit.labs.overthewire.org's password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

```bash
bandit3@bandit:~$ ls
inhere
```

```bash
bandit3@bandit:~$ cd inhere/
```

```bash
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Sep  1 06:30 .
drwxr-xr-x 3 root    root    4096 Sep  1 06:30 ..
-rw-r----- 1 bandit4 bandit3   33 Sep  1 06:30 .hidden
```

```bash
bandit3@bandit:~/inhere$ cat .hidden 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

## Notas adicionales
## Referencias