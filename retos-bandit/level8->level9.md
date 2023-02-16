# Level 8 -> level 9

## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit8**
Password: **TESKZC0XvTetK0S9xNwm25STk5iWrBvP**

## Solución
```bash
hone@Unidad03:~$ ssh bandit8@bandit.labs.overthewire.org -p 2220
```

```
bandit8@bandit.labs.overthewire.org's password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP 
```

```bash
andit8@bandit:~$ ls
data.txt
```

```propertibashes
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

## Notas adicionales
## Referencias
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)