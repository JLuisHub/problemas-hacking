# Level 10 -> 11

## Objetivo

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit10**

Password: **G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s**

## Solución

```bash
hone@Unidad03:~$ ssh bandit10@bandit.labs.overthewire.org -p 2220
```

```bash
bandit10@bandit.labs.overthewire.org's password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s 
```

```bash
bandit10@bandit:~$ ls
data.txt
```

```bash
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

## Notas adicionales

## Referencias

[Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)
