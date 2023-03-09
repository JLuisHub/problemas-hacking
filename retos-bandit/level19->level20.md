# Level 19 -> level 20

## Objetivo

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit19**

Password: **awhqfNnAbc1naukrpqDYcF95h7HoMTrC**

## Solución

```bash
hone@Unidad03:~$ ssh bandit19@bandit.labs.overthewire.org -p 2220
```

```bash
bandit19@bandit.labs.overthewire.org's password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC 
```

```bash
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rwsr-x---  1 bandit20 bandit19 14872 Sep  1 06:30 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
```

```bash
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

## Notas adicionales

## Referencias

[setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)

ls -la
"Se muestran archivos, entre ellos badir20-do"

./bandir20-do cat etc/bandit_pass/bandit20
'Muestra la contraseña en nombre del usuario bandit20 como usuario bandit19'
