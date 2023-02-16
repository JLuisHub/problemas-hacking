# Level 9-> level 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit9**
Password: **EN632PlfYiZbn3PhVK3XOGSlNInNE00t**

## Solución
```bash
hone@Unidad03:~$ ssh bandit9@bandit.labs.overthewire.org -p 2220
```

```
bandit9@bandit.labs.overthewire.org's password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t 
```

```bash
bandit9@bandit:~$ ls
data.txt
```

```bash
bandit9@bandit:~$ strings data.txt | grep ==
========== the
bu========== password
4iu========== is
b~==P
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

## Notas adicionales
## Referencias

