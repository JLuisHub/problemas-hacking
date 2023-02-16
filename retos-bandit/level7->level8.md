# Level 7 -> level 8

## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit7**
Password: **z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**

## Solución
```bash
one@Unidad03:~$ ssh bandit7@bandit.labs.overthewire.org -p 2220
```

```
bandit7@bandit.labs.overthewire.org's password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

```bash
bandit7@bandit:~$ ls
data.txt
```

```bash
bandit7@bandit:~$ grep millionth data.txt 
millionth	TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

## Notas adicionales
## Referencias