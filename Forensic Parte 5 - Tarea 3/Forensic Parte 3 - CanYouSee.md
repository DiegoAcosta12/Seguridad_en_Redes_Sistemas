**RETO:**  
CanYouSee

**DESCRIPCIÓN:**  
How about some hide and seek?

**SOLUCIÓN:**

1. **Descarga y extracción del archivo**:
    
    - Se descargó el archivo `unknown.zip` desde la URL proporcionada
        
    - Al descomprimir, se obtuvo el archivo `ukn_reality.jpg` (2.2 MB)
        
2. **Análisis inicial del archivo**:
    
    - El comando `file` confirmó que es un archivo JPEG válido
        
    - La búsqueda de strings con `grep -i "pico"` no devolvió resultados directos
        
    - El análisis con `binwalk` no mostró archivos embebidos evidentes
        
3. **Examen de metadatos EXIF**:
    
    - Se utilizó `exiftool` para analizar los metadatos de la imagen
        
    - En el campo **"Attribution URL"** se encontró un string codificado en Base64:  
        `cGljb0NURntNRTc0RDQ3QV9ISUREM05fYjMyMDQwYjh9Cg==`
        
4. **Descifrado del contenido oculto**:
    
    - El string Base64 se decodificó usando `base64 -d`
        
    - El resultado fue la flag en texto claro
        
5. **Verificación adicional**:
    
    - Se intentó usar `steghide` pero no se encontraron datos adicionales embebidos con contraseña
        
    - El análisis del final del archivo no reveló más información oculta
        

**FLAG OBTENIDA:**  
`picoCTF{ME74D47A_HIDD3N_b32040b8}`

**NOTAS ADICIONALES:**

- La flag `ME74D47A_HIDD3N_b32040b8` parece contener referencias hexadecimales y el mensaje "HIDDEN"
    
- Este reto demostró la técnica de **esteganografía en metadatos EXIF**
    
- Los metadatos EXIF (Exchangeable Image File Format) son comúnmente usados para ocultar información en retos CTF
    
- El campo "Attribution URL" fue utilizado de manera creativa para esconder la flag
    
- La codificación Base64 es frecuentemente utilizada para ocultar texto en formatos que requieren caracteres ASCII
    
- El reto enfatizó la importancia de revisar todos los metadatos de archivos multimedia en investigaciones forenses
    
- La herramienta `exiftool` resultó crucial para resolver este desafío
    
- No fue necesario usar técnicas más avanzadas de esteganografía como LSB (Least Significant Bit) o herramientas especializadas
    
- El tamaño de la imagen (4308x2875, 12.4 megapíxeles) podría haber sido una distracción, pero la solución estaba en los metadatos simples
    
- Este ejercicio ilustró que a veces la información oculta está en los lugares más evidentes pero menos examinados
    
- La lección principal: siempre verificar los metadatos de archivos en desafíos de esteganografía
    
- El formato de la flag sugiere que "ME74D47A" podría ser un valor hexadecimal y "b32040b8" otro identificador en hexadecimal
    
- El reto demostró efectivamente el concepto de "hide and seek" (escondite) mencionado en la descripción