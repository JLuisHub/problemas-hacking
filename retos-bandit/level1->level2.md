# Level 1 -> level 2

## Objetivo
The password for the next level is stored in a file called - located in the home directory

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit1**
Password: **NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL**

## Solución

```bash
hone@Unidad03:~$ ssh bandit1@bandit.labs.overthewire.org -p 2220
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames
```

```
bandit0@bandit.labs.overthewire.org's password: bandit0
```

```bash
bandit1@bandit:~$ ls
-
```

```bash
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

## Notas adicionales
## Referencias
-   [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
-   [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)