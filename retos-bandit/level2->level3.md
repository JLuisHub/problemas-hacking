# Level 2 -> level 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit2**
Password: **2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**

## Solución
```bash
hone@Unidad03:~$ ssh bandit2@bandit.labs.overthewire.org -p 2220 
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames
```

```
bandit2@bandit.labs.overthewire.org's password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

```bash
bandit2@bandit:~$ \> ls
spaces in this filename
```

```bash
bandit2@bandit:~$ cat 'spaces in this filename'
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```


## Notas adicionales
## Referencias
[Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)