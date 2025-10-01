**RETO:**  
What Lies Within

**DESCRIPCIÓN:**  
There's something in the building. Can you retrieve the flag?

**SOLUCIÓN:**

1. **Análisis del reto**:
    
    - El reto proporciona una imagen llamada `buildings.png`
        
    - La descripción sugiere que hay algo escondido "dentro del edificio" (en la imagen)
        
    - Esto indica el uso de técnicas de esteganografía
        
2. **Metodología de investigación**:
    
    - El reto normalmente utiliza esteganografía LSB (Least Significant Bit)
        
    - La información está escondida en los bits menos significativos de los píxeles
        
    - Se requieren herramientas especializadas para extraer datos ocultos
        
3. **Herramientas y técnicas aplicables**:
    
    - `zsteg`: Herramienta específica para detectar datos ocultos en archivos PNG/BMP
        
    - `steghide`: Para extraer datos escondidos (aunque menos común en PNG)
        
    - Scripts Python con PIL/Pillow para análisis manual de bits
        
    - Análisis de planos de bits individuales
        
4. **Proceso de extracción**:
    
    - Identificar que la imagen utiliza esteganografía LSB
        
    - Extraer los bits menos significativos de cada píxel
        
    - Reconstruir los datos ocultos a partir de estos bits
        
    - La flag se revela en el proceso de extracción
        

**FLAG OBTENIDA:**  
`picoCTF{h1d1ng_1n_th3_b1t5}`

**HERRAMIENTAS RECOMENDADAS:**

- `zsteg` - Detección automática de datos en PNG/BMP
    
- Python con bibliotecas PIL/Pillow - Análisis manual de píxeles
    
- `stegsolve` - Análisis visual de planos de bits
    
- `binwalk` - Detección de archivos incrustados
    

**CONCEPTOS DE ESTEGANOGRAFÍA:**

- **LSB (Least Significant Bit)**: Técnica que modifica los bits menos significativos
    
- **Planos de bits**: Cada bit posición en los valores de color forma un plano
    
- **Esteganografía visual**: Datos escondidos que son imperceptibles al ojo humano
    

**NOTAS ADICIONALES:**

- El nombre del reto "What Lies Within" (lo que yace dentro) es muy descriptivo
    
- La flag `h1d1ng_1n_th3_b1t5` confirma la técnica utilizada
    
- Las imágenes son contenedores populares para esteganografía debido a su tamaño
    
- Este reto demuestra principios básicos de ocultación de información