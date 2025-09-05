RETO:
Serpentine.

DESCRIPCION:
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/35/serpentine.py)

SOLUCION:
- Abrí `serpentine.py` en un editor de texto para inspeccionar su contenido.

- Encontré la variable `flag_enc` que contiene la flag cifrada y la función `str_xor` que la descifra usando la clave `'enkidu'`.

- Para obtener la flag, creé un pequeño script en Python que copiaba la variable `flag_enc` y aplicaba la función `str_xor`:


`def str_xor(secret, key):     new_key = key     i = 0     while len(new_key) < len(secret):         new_key += key[i]         i = (i + 1) % len(key)     return "".join([chr(ord(s) ^ ord(k)) for s,k in zip(secret,new_key)])  flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17) + chr(0x5e) + chr(0x5f) + chr(0x0d) + chr(0x3b) + chr(0x19) + chr(0x56) + chr(0x5b) + chr(0x5e) + chr(0x36) + chr(0x53) + chr(0x07) + chr(0x51) + chr(0x18) + chr(0x58) + chr(0x05) + chr(0x57) + chr(0x11) + chr(0x3a) + chr(0x0f) + chr(0x0e) + chr(0x59) + chr(0x06) + chr(0x4d) + chr(0x55) + chr(0x0c) + chr(0x0f) + chr(0x14)  flag = str_xor(flag_enc, 'enkidu') print(flag)`

- Ejecuté el script en Python y la flag se imprimió correctamente.

 **SOLUCION:** `picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}` 

NOTAS ADICIONALES:
- La opción del menú “b) Print flag” no funcionaba, por eso era necesario leer el código fuente.

- Aprendí que a veces los retos de Python esconden la flag en variables cifradas y requieren descifrado con claves internas del script.

REFERENCIAS:
https://docs.python.org/3/library/functions
https://stackoverflow.com/questions/10798419/perl-windows-watch-a-file-and-read-last-line/18581341#18581341