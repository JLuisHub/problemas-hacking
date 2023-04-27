# WebNet0

## Objetivo

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Solución

Se descargan los paquetes rastreados y la llave. Al abrir los paquetes con el programa WireShark se observa lo siguiente.

![img-01](im1.png)

Al utilizar la llave que se nos proporciona podemos desencriptar el protocolo TLS.

![img-02](img2.png)

Despues de puede buscar la palabra "picoCTF" como una cadena en los detalles de los paquetes para encontrar la bandera.

![img-03](img3.png)

Despues solo se tiene que copiar la bandera como texto imprimible para obtenerla.

Bandera: picoCTF{nongshim.shrimp.crackers}

## Referencias
