**RETO:** hideme

**DESCRIPCION:**  
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/261/flag.png).

**SOLUCION:**

1. Descargar el archivo `flag.png` desde la URL proporcionada.
    
2. Ejecutar `binwalk flag.png` para identificar archivos incrustados.
    
3. Observar que hay un archivo ZIP embebido que contiene un directorio `secret/` con otro `flag.png` dentro.
    
4. Extraer los archivos con `binwalk -e flag.png`.
    
5. Navegar al directorio extraído `_flag.png.extracted/secret/`.
    
6. Encontrar la flag escrita en el archivo `flag.png` extraído.
    

Flag: `picoCTF{Hiddinng_An_imag3_within_@n_ima9e_96539bea}`

**NOTAS ADICIONALES:**

- El archivo PNG original actúa como contenedor de otros archivos.
    
- No se necesitan contraseñas para extraer el contenido.
    
- La flag es visible directamente en la imagen extraída, sin requerir esteganografía avanzada.
    

**REFERENCIAS:**

- Herramienta utilizada: Binwalk - [http://github.com/ReFirmLabs/binwalk](http://github.com/ReFirmLabs/binwalk)