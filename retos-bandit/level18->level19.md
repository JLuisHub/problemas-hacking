# Level 18 -> level 19

## Objetivo

The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit18**

Password: **hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg**

## Solución

```bash
hone@Unidad03:~$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

```bash
bandit18@bandit.labs.overthewire.org's password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg 
```

```bash
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

## Notas adicionales

## Referencias
