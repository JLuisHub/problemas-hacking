# Level 0 -> level 1

## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Datos de acceso
Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit0**
Password: **bandit0**

## Solución

```bash
hone@Unidad03:~$ ssh bandit0@bandit.labs.overthewire.org -p 2220
```

```bash
bandit0@bandit:~$ ls
readme
```

```bash
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```


## Notas adicionales
|comando|Descricpicon|
|---|---|
|cat|Muestra el contenido de un archivo|
