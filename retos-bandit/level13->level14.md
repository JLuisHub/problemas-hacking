# Level 13 -> level 14

## Objetivo

The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit13**
Password: **wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw**

## Solución

```bash
hone@Unidad03:~$ ssh bandit13@bandit.labs.overthewire.org -p 2220
```

```bash
bandit13@bandit.labs.overthewire.org's password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw 
```

```bash
bandit13@bandit:~$ ls
sshkey.private
```

```bash
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
```

```bash
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

## Notas adicionales

## Referencias

[SSH/OpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)
