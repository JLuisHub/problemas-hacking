# Level 17 -> level 18

## Objetivo

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit17**

Password: **VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e**

## Solución

```bash
hone@Unidad03:~$ ssh bandit17@bandit.labs.overthewire.org -p 2220
```

```bash
bandit17@bandit.labs.overthewire.org's password: VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e 
```

```bash
bandit17@bandit:~$ diff passwords.old passwords.new 
42c42
09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

## Notas adicionales

## Referencias
