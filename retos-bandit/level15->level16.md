# Level 15 -> level 16

## Objetivo

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso

Host: **bandit.labs.overthewire.org** on port 2220
Username: **bandit15**
Password: **jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt**

## Solución

```bash
hone@Unidad03:~$ ssh bandit15@bandit.labs.overthewire.org -p 2220
```

```bash
bandit15@bandit.labs.overthewire.org's password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt 
```

```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
 Can't use SSL_get_servername
 depth=0 CN = localhost
 verify error:num=18:self-signed certificate
 verify return:1
 depth=0 CN = localhost
 verify error:num=10:certificate has expired
 notAfter=Sep  1 06:31:12 2022 GMT
 verify return:1
 depth=0 CN = localhost
 notAfter=Sep  1 06:31:12 2022 GMT
 verify return:1

[...

```

```bash
...]
    Start Time: 1662264624
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

```bash
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

```bash
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```

## Notas adicionales

## Referencias

- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)

openssl s_cliente -connect localhost:30001

"Se le da el password del nivel 15 y da el del 16"
