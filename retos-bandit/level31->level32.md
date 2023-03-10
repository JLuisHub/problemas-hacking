# Level 31-> level 32

## Objetivo

There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo`. The password for the user `bandit31-git` is the same as for the user `bandit31`.
Clone the repository and find the password for the next level.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit31**

Password: **OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt**

## Solución

```bash
hone@Unidad03:~$ ssh bandit31@bandit.labs.overthewire.org -p 2220
```

```bash
bandit31bandit.labs.overthewire.org's password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

```bash
bandit31@bandit:~$ mkdir /tmp/git-repo31
```

```bash
bandit31@bandit:~$ cd /tmp/git-repo31
```

```bash
bandit31@bandit:/tmp/git-repo31$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
```

```bash
bandit31-git@localhost's password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

```bash
bandit31@bandit:/tmp/git-repo31$ cd repo
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ ls
README.md
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 16 17:51 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 16 17:12 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 16 17:53 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 16 17:12 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Sep 16 17:51 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 16 17:12 README.md
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ rm .gitignore
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ echo "May I come in?" > key.txt
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ git add key.txt
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ git commit -m "subida"
[master 5e8642d] subida
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
```

```bash
bandit31@bandit:/tmp/git-repo31/repo$ git push 
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
```

```bash
bandit31-git@localhost's password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

```bash
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 319 bytes | 319.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
```

## Notas adicionales

## Referencias
