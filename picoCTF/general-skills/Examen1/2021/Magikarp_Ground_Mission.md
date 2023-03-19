# Magikarp Ground Mission

## Objetivo

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `a13b7f9d`

## Solución

```bash
hone@Unidad03:~$ ssh ctf-player@venus.picoctf.net -p 57616
```

```bash
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
```

```bash
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
```

```bash
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
```

```bash
ctf-player@pico-chall$ cd /
```

```bash
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64 media  mnt  opt  proc  root  run  sbin srv  sys  tmp  usr  var
```

```bash
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
```

```bash
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
```

```bash
ctf-player@pico-chall$ cd ~
```

```bash
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
```

```bash
ctf-player@pico-chall$ cat 3of3.flag.txt 
71be5264}
```

Bandera: *picoCTF{xxsh_0ut_0f_\\/\\/4t3r_71be5264}*

## Referencias
