**RETO:**  
information

**DESCRIPCIÓN:**  
Files can always be changed in a secret way. Can you find the flag?

**SOLUCIÓN:**

1. **Descarga del archivo**:
    
    - Se descargó el archivo `cat.jpg` desde la URL proporcionada
        
    - El archivo es una imagen JPEG de 858 KB con dimensiones 2560x1598 píxeles
        
2. **Análisis de metadatos EXIF**:
    
    - Se utilizó `exiftool` para examinar los metadatos del archivo
        
    - Se identificaron varios campos relevantes:
        
        - **Copyright Notice**: PicoCTF
            
        - **Rights**: PicoCTF
            
        - **License**: cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
            
3. **Identificación del método de ocultamiento**:
    
    - El campo "License" contenía un string que parecía estar codificado
        
    - El formato del string seguía el patrón típico de Base64
        
    - Los otros campos ("Copyright Notice" y "Rights") servían como pistas de que había información relacionada con PicoCTF
        
4. **Descifrado del contenido**:
    
    - El string `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9` se decodificó usando Base64
        
    - El resultado fue la flag en texto claro
        
5. **Verificación adicional**:
    
    - Se examinaron strings en el archivo confirmando referencias a "PicoCTF"
        
    - Se verificó que no había archivos embebidos usando `binwalk`
        
    - El análisis confirmó que la información estaba únicamente en los metadatos
        

**FLAG OBTENIDA:**  
`picoCTF{the_m3tadata_1s_modified}`

**NOTAS ADICIONALES:**

- La flag `the_m3tadata_1s_modified` traduce directamente a "the metadata is modified"
    
- Este reto demostró la técnica de **ocultamiento de información en metadatos EXIF**
    
- Los campos de metadatos como "License", "Copyright", y "Rights" son comúnmente utilizados para este propósito
    
- La codificación Base64 es ideal para este tipo de ocultamiento ya que produce strings que parecen legítimos en metadatos
    
- El reto enfatizó que los archivos pueden ser modificados de manera secreta sin afectar su funcionalidad principal
    
- La herramienta `exiftool` fue esencial para descubrir la información oculta
    
- No fue necesario usar técnicas de esteganografía complejas como manipulación de bits o análisis de frecuencia
    
- La presencia de "PicoCTF" en múltiples campos de metadatos sirvió como una pista importante
    
- Este ejercicio ilustró la importancia de examinar todos los metadatos disponibles en análisis forenses digitales
    
- La flag obtenida describe perfectamente el método de ocultamiento utilizado
    
- El reto mostró cómo información sensible puede ser escondida a simple vista en campos que normalmente no son examinados cuidadosamente
    
- La lección principal: siempre revisar metadatos exhaustivamente en investigaciones de seguridad
    
- La técnica demostrada es utilizada en escenarios reales para comunicación encubierta y marcado de archivos