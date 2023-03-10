# Level 29 -> level 30

## Objetivo

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit29**

Password: **tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S**

## Solución

```bash
hone@Unidad03:~$ ssh bandit29@bandit.labs.overthewire.org -p 2220
```

```bash
bandit29bandit.labs.overthewire.org's password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

```bash
bandit29@bandit:~$ mkdir /tmp/repo-git
```

```bash
bandit29@bandit:~$ cd /tmp/repo-git
```

```bash
bandit29@bandit:/tmp/repo-git$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
```

```bash
bandit29-git@localhost's password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

```bash
bandit29@bandit:/tmp/repo-git$ cd repo/
```

```bash
bandit29@bandit:/tmp/repo-git/repo$ ls
README.md
```

```bash
bandit29@bandit:/tmp/repo-git/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
```

```bash
bandit29@bandit:/tmp/repo-git/repo$ git checkout dev
Switched to branch 'dev'
Your branch is up to date with 'origin/dev'.
```

```bash
bandit29@bandit:/tmp/repo-git/repo$ git log
commit 2b1395f00cfb986163082c50100be5be8f249f64 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add data needed for development

commit 989df8073e16b5f7ec337f51bc1f60bd2f6b7e0b
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add gif2ascii

commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (origin/master, origin/HEAD, master)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md
```

```bash
bandit29@bandit:/tmp/repo-git/repo$ git show 2b1395f00cfb986163082c50100be5be8f249f64
commit 2b1395f00cfb986163082c50100be5be8f249f64 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials
 
 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
 
```

## Notas adicionales

## Referencias
