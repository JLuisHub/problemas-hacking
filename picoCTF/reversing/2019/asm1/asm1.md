# Nombre

## Objetivo

What does asm1(0x8be) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S)

## Solución

Se descarga el archivo y despues se puede observar que es codigo ensamblador

```bash
hone@unidad03:~/asm1$ cat test.S 
asm1:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	cmp    DWORD PTR [ebp+0x8],0x71c
	<+10>:	jg     0x512 <asm1+37>
	<+12>:	cmp    DWORD PTR [ebp+0x8],0x6cf
	<+19>:	jne    0x50a <asm1+29>
	<+21>:	mov    eax,DWORD PTR [ebp+0x8]
	<+24>:	add    eax,0x3
	<+27>:	jmp    0x529 <asm1+60>
	<+29>:	mov    eax,DWORD PTR [ebp+0x8]
	<+32>:	sub    eax,0x3
	<+35>:	jmp    0x529 <asm1+60>
	<+37>:	cmp    DWORD PTR [ebp+0x8],0x8be
	<+44>:	jne    0x523 <asm1+54>
	<+46>:	mov    eax,DWORD PTR [ebp+0x8]
	<+49>:	sub    eax,0x3
	<+52>:	jmp    0x529 <asm1+60>
	<+54>:	mov    eax,DWORD PTR [ebp+0x8]
	<+57>:	add    eax,0x3
	<+60>:	pop    ebp
	<+61>:	ret    

```

N1:
```
pila
Linea +0
---------
0000
[ 0x8be ]
[ ret 	]
[ 0x8be ]
ffff
---------
```

N2:
```
pila
+1
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------
```

N3:
```
pila
+3
+10
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------
```

N4:
```
pila
+37
+44
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------
```

N5:
```
pila
+46
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------

registers
[ 0x8be ] eax
```

N6:
```
pila
+49
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------

registers
[ 0x8bb ] eax
```

N7:
```
pila
+52
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------

registers
[ 0x8bb ] eax
```

N8:
```
pila
+52
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------

registers
[ 0x8bb ] eax
```

N9:
```
pila
+52
---------
[ 0000  ] <-esp <-ebp
[ ret   ] 		<-ebp + 0x4
[ 0x8be ] 		<-ebp + 0x8
ffff
---------

registers
[ 0x8bb ] eax -> Se saca
```

Bandera: *0x8bb*

## Referencias
