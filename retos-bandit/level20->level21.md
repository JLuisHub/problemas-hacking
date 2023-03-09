# Level 20 -> level 21

## Objetivo

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit20**
Password: **VxCazJaVykI6W36BkBU0mJTCM8rR95XT**

## Solución

```bash
hone@Unidad03:~$ ssh bandit20@bandit.labs.overthewire.org -p 2220
```

```bash
bandit20@bandit.labs.overthewire.org's password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT 
```

```bash
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15596 Sep  1 06:30 suconnect
```

```bash
bandit20@bandit:~$ cat /etc/bandit_pass/bandit20 | nc -lp 6000 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
> [1] 3839832
```

```bash
bandit20@bandit:~$ ./suconnect 6000
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    cat /etc/bandit_pass/bandit20 | nc -lp 6000 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

## Notas adicionales

## Referencias
