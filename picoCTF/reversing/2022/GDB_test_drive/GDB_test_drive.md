# GDB Test Drive

## Objetivo

Can you get the flag?
Download this [binary](https://artifacts.picoctf.net/c/86/gdbme).
Here's the test drive instructions:
- $ chmod +x gdbme
- $ gdb gdbme
- (gdb) layout asm
- (gdb) break *(main+99)
- (gdb) run
- (gdb) jump *(main+104)

## Solución

```bash
chmod +x gdbme
```

```bash
gdb gdbme
```

```bash
layout asm
```

```bash
(gdb) break *(main+99)
Breakpoint 1 at 0x132a
```

```bash
(gdb) run
Starting program: /GDB_test_drive/gdbme

Breakpoint 1, 0x000055555555532a in main ()
```

```bash
(gdb) jump *(main+104)
Continuing at 0x55555555532f.
picoCTF{d3bugg3r_dr1v3_72bd8355}
```

Bandera: *picoCTF{d3bugg3r_dr1v3_72bd8355}*

## Referencias
