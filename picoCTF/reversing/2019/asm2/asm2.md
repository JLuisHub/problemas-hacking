# asm2

## Objetivo

What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. Source

## Solución

Parametros:
asm2(0xb,0x2e)

```bash
hone@unidad03:~/asm2$ cat test.S 
asm2:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	sub    esp,0x10
	<+6>:	mov    eax,DWORD PTR [ebp+0xc]
	<+9>:	mov    DWORD PTR [ebp-0x4],eax
	<+12>:	mov    eax,DWORD PTR [ebp+0x8]
	<+15>:	mov    DWORD PTR [ebp-0x8],eax
	<+18>:	jmp    0x509 <asm2+28>
	<+20>:	add    DWORD PTR [ebp-0x4],0x1
	<+24>:	sub    DWORD PTR [ebp-0x8],0xffffff80
	<+28>:	cmp    DWORD PTR [ebp-0x8],0x63f3
	<+35>:	jle    0x501 <asm2+20>
	<+37>:	mov    eax,DWORD PTR [ebp-0x4]
	<+40>:	leave  
	<+41>:	ret    
```

N1:
```
pila
+1
---------
[   ebp     ]   <-- esp <-ebp
[   retorno ]
[   0xb     ]
[   0x2e    ]
ffff
---------

registers
[  ]
```

N2:
```
pila
+3
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[           ]   <-- ebp -0x8
[           ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[  ]
```

N3:
```
pila
+6
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[           ]   <-- ebp -0x8
[           ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0x2e ]
```

N4:
```
pila
+9
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[           ]   <-- ebp -0x8
[   0x2e    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0x2e ]
```

N5:
```
pila
+12
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[           ]   <-- ebp -0x8
[   0x2e    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N6:
```
pila
+15
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0xb     ]   <-- ebp -0x8
[   0x2e    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N7:
```
pila
+18
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0xb     ]   <-- ebp -0x8
[   0x2e    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N8:
```
pila
+28
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0xb     ]   <-- ebp -0x8
[   0x2e    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N9:
```
pila
+20
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0xb     ]   <-- ebp -0x8
[   0x2f    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N10:
```
pila
+24
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0x8b     ]   <-- ebp -0x8
[   0x2f    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N11:
```
pila
+28
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0x8b    ]   <-- ebp -0x8
[   0x2f    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

...

N12:
```
pila
+28
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0x8b    ]   <-- ebp -0x8
[   0xf6    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xb ]
```

N13:
```
pila
+37
---------
[           ]   <-- esp
[           ]   <-- ebp -0xc
[   0x8b    ]   <-- ebp -0x8
[   0xf6    ]   <-- ebp -0x4
[   ebp     ]   <-- ebp
[   retorno ]   <-- ebp +0x4
[   0xb     ]   <-- ebp +0x8
[   0x2e    ]   <-- ebp +0xc
ffff
---------

registers
[ 0xf6 ]
```

Bandera: *0xf6*

## Referencias
