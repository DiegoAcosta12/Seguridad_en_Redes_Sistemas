**RETO:**  
Glory of the Garden

**DESCRIPCIÓN:**  
This garden contains more than it seems. What is a hex editor?

**SOLUCIÓN:**

1. **Descarga y verificación del archivo**:
    
    - Descargué el archivo `garden.jpg` en mi computadora local con Windows
        
    - El archivo parecía ser una imagen JPEG normal
        
2. **Análisis del archivo**:
    
    - Utilicé el Bloc de notas de Windows para abrir el archivo `garden.jpg`
        
    - Al abrir un archivo binario como texto, se pueden ver datos legibles mezclados con caracteres especiales
        
    - Realicé una búsqueda (Ctrl + F) del texto "pico" dentro del archivo
        
3. **Extracción de la flag**:
    
    - La búsqueda reveló la flag ubicada al final del contenido del archivo
        
    - La flag estaba embebida directamente en los datos del archivo JPEG
        
    - No fue necesario usar herramientas avanzadas como editores hexadecimales
        

**FLAG OBTENIDA:**  
`picoCTF{more_than_m33ts_the_3y3657BaB2C}`

**HERRAMIENTAS UTILIZADAS:**

- Bloc de notas de Windows - Para visualizar el contenido como texto
    
- Función de búsqueda (Ctrl + F) - Para localizar rápidamente la flag
    

**CONCEPTOS APRENDIDOS:**

- Los archivos de imagen pueden contener datos de texto embebidos
    
- Las herramientas básicas del sistema pueden ser suficientes para resolver retos simples
    
- La flag hace referencia a que hay "más de lo que parece" en la imagen
    
- No siempre se necesitan herramientas especializadas para esteganografía básica
    

**NOTAS ADICIONALES:**

- El nombre del reto "Glory of the Garden" es un juego de palabras
    
- La técnica utilizada fue simple: datos de texto almacenados al final de un archivo JPEG
    
- Este enfoque demuestra que a veces las soluciones más simples son las más efectivas
    
- La flag única obtenida confirma que cada instancia del reto tiene una flag diferente