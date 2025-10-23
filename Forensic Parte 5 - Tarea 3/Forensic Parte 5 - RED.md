**RETO:** RED

**DESCRIPCION:** RED, RED, RED, RED. Download the image: red.png. The challenge involves finding a hidden flag in the image using steganography techniques.

**SOLUCION:**

- Descargué la imagen red.png usando wget
    
- Usé **`zsteg`** para analizar esteganografía en la imagen PNG
    
- Encontré datos ocultos en LSB (Least Significant Bit) del canal rgba
    
- El dato era un string en Base64: `cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==`
    
- Decodifiqué el Base64 con `base64 -d` para obtener la flag
    

Comandos usados:

bash

wget https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png
zsteg red.png
echo "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d

**Flag:** `picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}`

**NOTAS ADICIONALES:**

- La flag estaba oculta usando LSB steganography en el canal rgba de la imagen
    
- El poema en los metadatos era una distracción
    
- La pista "RED" se refería al canal de color donde estaba oculta la información
    
- zsteg es una herramienta especializada para detectar steganografía en PNG/BMP
    

**REFERENCIAS:**

- [https://github.com/zed-0xff/zsteg](https://github.com/zed-0xff/zsteg)
    
- [https://en.wikipedia.org/wiki/Steganography](https://en.wikipedia.org/wiki/Steganography)