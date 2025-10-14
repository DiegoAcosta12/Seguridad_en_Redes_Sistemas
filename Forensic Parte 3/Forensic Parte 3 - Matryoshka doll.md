**RETO:**  
Matryoshka doll

**DESCRIPCIÓN:**  
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: this

**SOLUCIÓN:**

1. **Análisis inicial del archivo**:
    
    - El archivo `dolls.jpg` se identificó como PNG image data (594 x 1104) a pesar de su extensión .jpg
        
    - El análisis con `binwalk` reveló un archivo ZIP incrustado en el offset `0x4286C`
        
    - El ZIP contenía la imagen `base_images/2_c.jpg`, iniciando el patrón de muñecas anidadas
        
2. **Proceso recursivo de extracción**:
    
    - **Nivel 1**: `dolls.jpg` → contenía → `2_c.jpg` (526 x 1106)
        
    - **Nivel 2**: `2_c.jpg` → contenía → `3_c.jpg` (428 x 1104)
        
    - **Nivel 3**: `3_c.jpg` → contenía → `4_c.jpg` (320 x 768)
        
    - **Nivel 4**: `4_c.jpg` → contenía → `flag.txt`
        
3. **Técnicas de extracción**:
    
    - Se utilizó `binwalk` para detectar archivos incrustados en cada imagen
        
    - Se empleó `dd` con los offsets específicos para extraer manualmente los archivos ZIP
        
    - Cada ZIP se descomprimió con `unzip` para revelar la siguiente muñeca
        
4. **Obtención de la flag**:
    
    - La última imagen (`4_c.jpg`) contenía un ZIP con el archivo `flag.txt`
        
    - La extracción y lectura del archivo reveló la flag final
        

**FLAG OBTENIDA:**  
`picoCTF{ac0072c423ee13bfc0b166af72e25b61}`

**NOTAS ADICIONALES:**

- Este reto demostró perfectamente el concepto de archivos anidados como muñecas matryoshka
    
- Cada imagen sucesiva era progresivamente más pequeña en dimensiones y tamaño de archivo
    
- La esteganografía se implementó mediante archivos ZIP incrustados dentro de imágenes PNG
    
- El uso de extensiones engañosas (.jpg para archivos PNG) añadió una capa adicional de ofuscación
    
- La resolución requirió un método sistemático y paciencia para extraer cada nivel recursivamente
    
- Herramientas esenciales incluyeron `binwalk` para detección, `dd` para extracción precisa, y `unzip` para descompresión
    
- La flag representa la culminación exitosa del viaje a través de las múltiples capas de archivos anidados