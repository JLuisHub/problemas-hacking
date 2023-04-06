# m00nwalk

## Objetivo

Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Solución

Al oprimir el link, se descarga un archivo de aurio **wav**, y se realiza lo siguiente.

```bash
hone@Unidad03:~/m00nwalk$ sstv -d message.wav -o imagen.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...             [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
```

```bash
hone@Unidad03:~/m00nwalk$ ls
imagen.png  m00nwalk.md  message.wav
```

```bash
hone@Unidad03:~/m00nwalk$ open imagen.png 
```

Al abrir la imagen, se puede observar una imagen con la bandera.
![imagen](imagen.png)

Bandera: *picoCTF{beep_boop_im_in_space}*

## Referencias
