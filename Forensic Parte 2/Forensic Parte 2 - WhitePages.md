**RETO:**  
WhitePages

**DESCRIPCIÓN:**  
I stopped using YellowPages and moved onto WhitePages... but the page they gave me is all blank!

**SOLUCIÓN:**

1. **Análisis del archivo aparentemente en blanco**:
    
    - El archivo `whitepages.txt` parecía estar vacío pero tenía 2982 bytes de tamaño
        
    - El análisis hexadecimal reveló dos tipos de espacios diferentes:
        
        - Espacio normal: `20` (hex)
            
        - Espacio em (U+2003): `e2 80 83` (hex)
            
2. **Decodificación del código binario**:
    
    - Los diferentes tipos de espacios representaban dígitos binarios
        
    - Después de probar diferentes combinaciones, se encontró que:
        
        - Espacio em (U+2003) = `0`
            
        - Espacio normal = `1`
            
3. **Conversión a texto**:
    
    - Los datos binarios se agruparon en bytes de 8 bits
        
    - Cada byte se convirtió a su carácter ASCII correspondiente
        
    - El proceso reveló un mensaje que contenía la flag
        

**FLAG OBTENIDA:**  
`picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}`

**NOTAS ADICIONALES:**

- La flag `not_all_spaces_are_created_equal` describe perfectamente la técnica de esteganografía utilizada
    
- Este reto demostró el uso de caracteres Unicode similares para ocultar información
    
- La esteganografía basada en espacios en blanco es difícil de detectar visualmente
    
- El método aprovechó que los espacios em (U+2003) y espacios normales (U+0020) son visualmente idénticos pero binariamente diferentes
    
- Esta técnica podría usarse para ocultar mensajes en documentos que parecen estar en blanco