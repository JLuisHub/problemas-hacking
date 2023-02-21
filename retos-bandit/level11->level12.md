# Level 11 -> level 12

## Objetivo

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit11**

Password: **6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**

## Solución

```bash
hone@Unidad03:~$ ssh bandit11@bandit.labs.overthewire.org -p 2220
```

```bash
bandit11@bandit.labs.overthewire.org's password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM 
```

```bash
bandit11@bandit:~$ ls
data.txt
```

```bash
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
```

```bash
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
```

```bash
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

## Notas adicionales

## Referencias

[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)
