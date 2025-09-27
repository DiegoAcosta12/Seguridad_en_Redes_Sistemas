**RETO:**  
Roboto Sans

**DESCRIPCIÓN:**  
The flag is somewhere on this web application not necessarily on the website. Find it.  
[http://saturn.picoctf.net:58972](http://saturn.picoctf.net:58972/)

**SOLUCIÓN:**

1. **Reconocimiento inicial**:
    
    - Identifiqué que el archivo `robots.txt` devolvía contenido HTML inusual
        
    - Al descargarlo correctamente como texto plano, encontré strings codificadas en Base64
        
2. **Análisis de robots.txt**:
    
    - Decodifiqué las strings Base64: `ZmxhZzEudHh0` → `flag1.txt` y `anMvbXlmaWxlLnR4dA==` → `js/myfile.txt`
        
    - El archivo `flag1.txt` no existía, pero `js/myfile.txt` estaba accesible
        
3. **Obtención de la flag**:
    
    - Accedí a `http://saturn.picoctf.net:58972/js/myfile.txt`
        
    - El archivo contenía la flag directamente
        

**FLAG OBTENIDA:**  
`picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de revisar archivos de configuración como robots.txt
    
- La información codificada en Base64 puede revelar rutas y archivos ocultos
    
- La flag hace referencia a "Who Doesn't Like Robots" (90B0T5)