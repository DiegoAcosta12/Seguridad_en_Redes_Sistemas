**RETO:**  
c0rrupt

**DESCRIPCIÓN:**  
We found this file. Recover the flag.

**SOLUCIÓN:**

1. **Análisis inicial del archivo**:
    
    - El archivo `mystery` fue identificado como datos binarios sin formato específico
        
    - El análisis con `xxd` reveló que los primeros bytes correspondían a un archivo PNG corrupto
        
    - El magic number del PNG estaba dañado: `89 65 4E 34` en lugar de `89 50 4E 47`
        
2. **Reparación del header PNG**:
    
    - Reemplacé los primeros 8 bytes corruptos con el header PNG correcto: `89 50 4E 47 0D 0A 1A 0A`
        
    - Identifiqué que el chunk IHDR también estaba corrupto: `43 22 44 52` en lugar de `49 48 44 52`
        
    - Reparé el chunk IHDR cambiándolo a `49 48 44 52` ("IHDR" en ASCII)
        
3. **Verificación y obtención de la flag**:
    
    - Después de las reparaciones, el archivo fue reconocido como "PNG image data"
        
    - La flag fue recuperada del archivo de imagen reparado
        

**FLAG OBTENIDA:**  
`picoCTF{C0rrupt10n_1847995}`

**NOTAS ADICIONALES:**

- La flag `C0rrupt10n` describe perfectamente la naturaleza del reto sobre archivos corruptos
    
- Este reto demostró la importancia de entender los formatos de archivo a nivel binario
    
- La reparación requirió conocimiento de la estructura de archivos PNG, incluyendo magic numbers y chunks
    
- Los chunks IHDR y IDAT son esenciales para la integridad de las imágenes PNG
    
- La corrupción de headers es un problema común que puede evitar que los archivos sean reconocidos por sus aplicaciones nativas