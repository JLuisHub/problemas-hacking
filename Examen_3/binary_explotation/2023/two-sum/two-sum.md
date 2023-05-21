# two-sum

## Objetivo

Can you solve this?
What two positive numbers can make this possible: n1 > n1 + n2 OR n2 > n1 + n2

## Solución

La manera para cumplir a la vez y a la vez no con estas condiciones es sobrepasar el limite de almacenamiento de un *int* 2^32

```bash
hone@unidad03:~/Documentos/Materias/Seguridad_Redes_Sistemas/problemas-hacking/Examen_3/binary_explotation/exclusive/two-sum$ nc saturn.picoctf.net 54868
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 
2147483647
1
You entered 2147483647 and 1
You have an integer overflow
YOUR FLAG IS: picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_e06700c0}
```

Bandera: *picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_e06700c0}*

## Referencias

[Reference](Link)
