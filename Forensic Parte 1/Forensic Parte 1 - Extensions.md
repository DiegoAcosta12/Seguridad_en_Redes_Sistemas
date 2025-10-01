**RETO:**  
Extensions

**DESCRIPCIÓN:**  
This is a really weird text file TXT? Can you find the flag?

**SOLUCIÓN:**

1. **Análisis inicial del archivo**:
    
    - Descargué el archivo `flag.txt` que supuestamente era un archivo de texto
        
    - Al usar el comando `file` descubrí que en realidad era una imagen PNG con extensión incorrecta
        
    - El encabezado del archivo mostraba la firma característica de PNG (`‰PNG`)
        
2. **Cambio de extensión**:
    
    - Renombré el archivo a la extensión correcta: `flag.png`
        
    - Verifiqué que el sistema ahora lo reconociera como imagen PNG
        
3. **Extracción de la flag**:
    
    - Utilicé el comando `strings` para buscar texto legible dentro del archivo binario
        
    - La flag fue revelada al examinar el contenido de la imagen
        

**FLAG OBTENIDA:**  
`picoCTF{now_you_know_about_extensions}`

**HERRAMIENTAS UTILIZADAS:**

- `file` - Para identificar el tipo real del archivo
    
- `strings` - Para extraer texto de archivos binarios
    
- `cp` - Para cambiar la extensión del archivo
    

**CONCEPTOS APRENDIDOS:**

- Las extensiones de archivo pueden ser engañosas y no siempre reflejan el tipo real
    
- Los archivos tienen "firmas mágicas" (magic numbers) que identifican su formato real
    
- Herramientas como `file` y `strings` son esenciales para análisis forense
    
- La flag hace referencia al aprendizaje sobre extensiones de archivo
    

**NOTAS ADICIONALES:**

- Este reto demuestra la importancia de verificar el tipo real de los archivos
    
- En seguridad, los atacantes a menudo usan extensiones engañosas para evadir detección
    
- El comando `file` ignora la extensión y analiza el contenido real del archivo