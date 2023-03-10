# Level 29 -> level 30

## Objetivo

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit30**

Password: **xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS**

## Solución

```bash
hone@Unidad03:~$ ssh bandit30@bandit.labs.overthewire.org -p 2220
```

```bash
bandit30bandit.labs.overthewire.org's password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

```bash
bandit30@bandit:~$ mkdir /tmp/rpgit
```

```bash
bandit30@bandit:~$ cd /tmp/rpgit
```

```bash
bandit30@bandit:/tmp/rpgit$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
```

```bash
bandit30-git@localhost's password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

```bash
bandit30@bandit:/tmp/rpgit$ cd repo/
```

```bash
bandit30@bandit:/tmp/rpgit/repo$ ls
README.md
```

```bash
bandit30@bandit:/tmp/rpgit/repo$ cat README.md 
just an epmty file... muahaha
```

```bash
bandit30@bandit:/tmp/rpgit/repo$ git tag
secret
```

```bash
bandit30@bandit:/tmp/rpgit/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

## Notas adicionales

## Referencias
