**RETO:** St3g0

**DESCRIPCION:**  
Download this image and find the flag.

**SOLUCION:**

- Descargué la imagen pico.flag.png usando wget
    
- Usé `strings` para buscar texto visible, sin resultados
    
- Usé **`zsteg`** para analizar esteganografía LSB en la imagen PNG
    
- Encontré la flag directamente en el canal `b1,rgb,lsb,xy`
    

Comandos usados:

bash

wget https://artifacts.picoctf.net/c/217/pico.flag.png
zsteg pico.flag.png

**Flag:** `picoCTF{7h3r3_15_n0_5p00n_a9a181eb}`

**NOTAS ADICIONALES:**

- La flag estaba oculta usando LSB steganography en los canales RGB
    
- El final del mensaje oculto era `$t3g0` como indicaba la pista
    
- No fue necesario extraer una imagen secundaria, `zsteg` mostró la flag directamente en texto
    
- El nombre del reto "St3g0" hace referencia a steganography
    

**REFERENCIAS:**

- [https://github.com/zed-0xff/zsteg](https://github.com/zed-0xff/zsteg)