**RETO:**  
So Meta

**DESCRIPCIÓN:**  
Find the flag in this picture.

**SOLUCIÓN:**

1. **Descarga y ubicación del archivo**:
    
    - Tuve el archivo `pico_img.png` descargado en mi computadora local
        
    - El archivo se encontraba en la carpeta de descargas
        
2. **Análisis de metadatos**:
    
    - Utilicé el Bloc de notas de Windows para abrir el archivo PNG
        
    - Al abrir la imagen como texto, pude visualizar tanto los datos binarios de la imagen como los metadatos embebidos
        
    - Realicé una búsqueda directa (Ctrl + F) del término "pico" dentro del contenido del archivo
        
3. **Extracción de la flag**:
    
    - La búsqueda reveló la flag ubicada en los metadatos del archivo
        
    - La flag estaba almacenada en formato de texto plano dentro de la estructura del archivo PNG
        
    - No fue necesario utilizar herramientas especializadas de análisis EXIF
        

**FLAG OBTENIDA:**  
`picoCTF{s0_m3ta_eb36bf44}`

**HERRAMIENTAS UTILIZADAS:**

- Bloc de notas de Windows - Para visualizar el contenido del archivo
    
- Función de búsqueda integrada (Ctrl + F) - Para localizar la flag rápidamente
    

**CONCEPTOS APRENDIDOS:**

- Los archivos PNG pueden contener metadatos en formato de texto
    
- Los metadatos EXIF y otros datos embebidos son accesibles con herramientas básicas
    
- El nombre del reto "So Meta" hace referencia directa a los metadatos (metadata)
    
- Las imágenes no solo contienen datos visuales sino también información textual
    

**NOTAS ADICIONALES:**

- La flag `s0_m3ta_eb36bf44` confirma que el reto trata sobre metadatos
    
- El sufijo `eb36bf44` es único para esta instancia del reto
    
- Este método demuestra que herramientas simples pueden ser efectivas para análisis básico
    
- Los metadatos en imágenes pueden revelar información sensible sobre el origen y edición del archivo