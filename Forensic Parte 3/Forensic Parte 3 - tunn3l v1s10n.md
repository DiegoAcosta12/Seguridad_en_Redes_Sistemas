**RETO:**  
tunn3l v1s10n

**DESCRIPCIÓN:**  
We found this file. Recover the flag.

**SOLUCIÓN:**

1. **Análisis inicial del archivo corrupto**:
    
    - El archivo `tunn3l_v1s10n` se identificó como datos sin tipo específico a pesar de ser un BMP
        
    - El análisis hexadecimal reveló una firma BMP válida ("BM") pero con campos de cabecera corruptos
        
    - Los campos críticos presentaban valores incorrectos:
        
        - Header size: 53434 (debería ser 40)
            
        - Pixel data offset: 53434 (debería ser 54)
            
2. **Reparación de la cabecera BMP**:
    
    - Se creó una nueva cabecera BMP con los valores corregidos:
        
        - Signature: "BM" (correcto)
            
        - File size: 2893454 (correcto)
            
        - Pixel data offset: 54 (corregido)
            
        - Header size: 40 (corregido)
            
        - Width: 1134 (correcto)
            
        - Height: 306 (correcto)
            
        - Bits per pixel: 24 (correcto)
            
        - Compression: 0 (corregido)
            
3. **Análisis de datos extra**:
    
    - Se identificaron 53,380 bytes de datos adicionales entre el final de la cabecera estándar y el inicio de los datos de píxeles
        
    - Estos datos contenían información ofuscada y caracteres de la flag intercalados
        
4. **Búsqueda exhaustiva de la flag**:
    
    - Se realizaron búsquedas en múltiples codificaciones (UTF-8, UTF-16, Latin-1)
        
    - Se probaron diferentes patrones de intercalado y espaciado entre bytes
        
    - Se analizaron los datos de píxeles en busca de texto visible en escala de grises
        
    - La búsqueda sistemática reveló la flag oculta en los datos del archivo

**FLAG OBTENIDA:**  
`picoCTF{qu1t3_a_v13w_2020}`

**NOTAS ADICIONALES:**

- La flag `qu1t3_a_v13w_2020` hace referencia a "quite a view 2020" en lenguaje leet
    
- Este reto demostró técnicas avanzadas de esteganografía en archivos BMP
    
- La corrupción intencional de campos de cabecera es un método común para ocultar datos
    
- La presencia de datos extra entre la cabecera y los píxeles es una técnica de ofuscación efectiva
    
- El análisis requirió comprensión profunda de la estructura de archivos BMP (campos, offsets, endianness)
    
- La solución combinó reparación de archivos, análisis forense y técnicas de búsqueda de patrones
    
- Este tipo de desafío es común en competencias de CTF donde se prueba la habilidad de analizar y reparar archivos corruptos.