**RETO:** Scan Surprise

**DESCRIPCION:** I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? The flag is hidden in a QR code image that needs to be scanned to reveal the text.

**SOLUCION:**

- Descargué el archivo challenge.zip que contenía una imagen flag.png
    
- La imagen resultó ser un código QR que contenía la flag
    
- Usé **`zbarimg`** para escanear y decodificar el código QR
    
- El comando `zbarimg flag.png` leyó directamente el contenido del QR y mostró la flag
    

Comandos usados:

bash

wget https://artifacts.picoctf.net/c_atlas/14/challenge.zip
unzip challenge.zip
cd home/ctf-player/drop-in/
zbarimg flag.png

**Flag:** `picoCTF{p33k_@_b00_0194a007}`

**NOTAS ADICIONALES:**

- Los códigos QR pueden almacenar diferentes tipos de datos, no solo URLs
    
- zbar-tools es una suite de herramientas de línea de comandos para procesar códigos de barras y QR
    
- También se puede usar la conexión SSH proporcionada: `ssh -p 54004 ctf-player@atlas.picoctf.net` con password `84b12bae`
    

**REFERENCIAS:**

- [https://linux.die.net/man/1/zbarimg](https://linux.die.net/man/1/zbarimg)
    
- [https://en.wikipedia.org/wiki/QR_code](https://en.wikipedia.org/wiki/QR_code)