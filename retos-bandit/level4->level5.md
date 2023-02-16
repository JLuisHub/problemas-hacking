# Level 4 -> level 5

## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit4**
Password: **2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**

## Solución
```bash
hone@Unidad03:~$ ssh bandit4@bandit.labs.overthewire.org -p 2220
```

```
bandit4@bandit.labs.overthewire.org's password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

```bash
bandit4@bandit:~$ ls
inhere
```

```bash
andit4@bandit cd inhere/
```

```properties
bandit4@bandit:~/inhere$ ls -la
total 48
drwxr-xr-x 2 root    root    4096 May  7  2020 .
drwxr-xr-x 3 root    root    4096 May  7  2020 ..
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file00
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file01
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file02
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file03
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file04
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file05
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file06
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file07
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file08
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file09
```

```properties
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```

```properties
bandit4@bandit:~/inhere$** cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

## Notas adicionales
## Referencias