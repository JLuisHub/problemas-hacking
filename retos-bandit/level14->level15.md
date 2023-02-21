# Level 14 -> level 15

## Objetivo

The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit14**
Password: **fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq**

## Solución

```bash
hone@Unidad03:~$ ssh bandit14@bandit.labs.overthewire.org -p 2220
```

```bash
bandit14@bandit.labs.overthewire.org's password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq 
```

```bash
bandit14@bandit:~$ nc -v localhost 30000
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
```

```
(Password del usuario actual)> fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

```bash
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

## Notas adicionales

## Referencias

- [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc)
- [IP Addresses](http://computer.howstuffworks.com/web-server5.htm)
- [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP_address)
- [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
- [Ports](http://computer.howstuffworks.com/web-server8.htm)
- [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))
