**RETO:**  
like1000

**DESCRIPCIÓN:**  
This .tar file got tarred a lot.

**SOLUCIÓN:**

1. **Análisis del problema**:
    
    - El reto involucraba un archivo `1000.tar` que contenía archivos tar anidados múltiples veces
        
    - La estructura consistía en `1000.tar` → `999.tar` → `998.tar` → ... hasta llegar al archivo final con la flag
        
    - Entre los archivos tar anidados se encontraban archivos `filler.txt` como distracción
        
2. **Proceso de extracción**:
    
    - Se implementó un método de extracción recursiva automática
        
    - El proceso extrajo cada nivel de archivo tar sucesivamente
        
    - Después de múltiples niveles de extracción, se encontró el archivo final que contenía la flag
        
3. **Obtención de la flag**:
    
    - La flag fue recuperada del archivo final en la secuencia de extracción
        
    - El proceso requirió paciencia debido a los múltiples niveles de anidamiento
        

**FLAG OBTENIDA:**  
`picoCTF{l0t5_0f_TAR5}`

**NOTAS ADICIONALES:**

- La flag `l0t5_0f_TAR5` (lots of TARs) describe perfectamente la naturaleza del reto
    
- Este desafío demostró el concepto de archivos comprimidos anidados múltiples veces
    
- La automatización mediante scripts fue esencial para manejar eficientemente los 1000 niveles de extracción
    
- Los archivos `filler.txt` sirvieron como elementos de distracción durante el proceso de extracción