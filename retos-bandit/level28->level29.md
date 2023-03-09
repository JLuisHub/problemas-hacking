# Level 28 -> level 29

## Objetivo

There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit28**

Password: **AVanL161y9rsbcJIsFHuw35rjaOM19nR**

## Solución

```bash
hone@Unidad03:~$ ssh bandit28@bandit.labs.overthewire.org -p 2220
```

```bash
bandit228bandit.labs.overthewire.org's password: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

```bash
bndit28@bandit:~$ mkdir /tmp/repo-on
```

```bash
bandit28@bandit:~$ cd /tmp/repo-on
```

```bash
bandit28@bandit:/tmp/repo-on$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
```

```bash
bandit28@bandit:/tmp/repo-on$ ls
repo
```

```bash
bandit28@bandit:/tmp/repo-on$ cd repo/
```

```bash
bandit28@bandit:/tmp/repo-on/repo$ ls
README.md
```

```bash
bandit28@bandit:/tmp/repo-on/repo$ git log
commit 43032edb2fb868dea2ceda9cb3882b2c336c09ec (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    fix info leak

commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

commit 43d032b360b700e881e490fbbd2eee9eccd7919e
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:24 2022 +0000

    initial commit of README.md
```

```bash
bandit28@bandit:/tmp/repo-on/repo$ git show bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: <TBD>
+- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

## Notas adicionales

## Referencias
