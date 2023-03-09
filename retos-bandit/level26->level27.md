# Level 26 -> level 27

## Objetivo

Good job getting a shell! Now hurry and grab the password for bandit27!

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit26**

Password: **c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1**

## Solución

```bash
hone@Unidad03:~$ ssh bandit26@bandit.labs.overthewire.org -p 2220
```

Antes de colocar la contraseña, es necesario aplicar el truco del ejercicio anterior, reduciendo el tamaño de la terminal y en seguida, colocar la contraseña.

```bash
bandit26@bandit.labs.overthewire.org's password: c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

Mostrado el editor de vi, se oprime la tecla V.
Se introduce el comando en vi

```bash
:set shell=/bin/bash
```

y el siguiente

```bash
shell
```

```bash
[No write since last change]
bandit26@bandit:~$ 
```

Nos regreso a la linea de comandos

```bash
bandit26@bandit:~$ ls
bandit27-do  text.txt
```

```bash
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```

## Notas adicionales

## Referencias
