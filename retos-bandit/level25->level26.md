# Level25 -> level26

## Objetivo

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220

Username: **bandit25**

Password: **p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d**

## Solución

```bash
hone@Unidad03:~$ ssh bandit25@bandit.labs.overthewire.org -p 2220
```

```bash
bandit25@bandit.labs.overthewire.org's password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```

```bash
bandit25@bandit:~$ ls
bandit26.sshkey
```

Antes de seguir, es necesario aplicar un truco, consiste en reducir el tamaño de la terminal para asi descubrir que se esta utilizando "vi" para aparentar que es esta iniciando secion.

```bash
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220
```

Seguido de esto, es necesario oprimir la tecla v y se mostrara el editor vi donde se introduce el siguiente comando:

```
:e /etc/bandit_pass/bandit26
```

```bash
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

## Notas adicionales

## Referencias
