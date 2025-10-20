**RETO:**  
interencdec

**DESCRIPCIÓN:**  
Can you get the real meaning from this file.

**SOLUCIÓN:**

1. **Descarga y análisis inicial del archivo**:
    
    - Se descargó el archivo `enc_flag` desde la URL proporcionada
        
    - El comando `file enc_flag` identificó el archivo como texto ASCII
        
    - El contenido inicial era: `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgya3lNRFJvYTJvMmZRPT0nCg==`
        
2. **Identificación de codificaciones múltiples**:
    
    - El nombre del reto "interencdec" sugirió múltiples capas de codificación
        
    - El formato del texto indicaba codificación Base64
        
    - Se aplicó la primera decodificación Base64 obteniendo: `b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='`
        
3. **Extracción y segunda decodificación**:
    
    - El resultado anterior era un string de Python bytes que contenía más Base64
        
    - Se extrajo el contenido entre comillas: `d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ==`
        
    - Se aplicó la segunda decodificación Base64 obteniendo: `wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6}`
        
4. **Análisis del cifrado final**:
    
    - El texto resultante tenía formato de flag pero estaba cifrado
        
    - Se identificó que "JAM" debería corresponder a "CTF" en una flag válida
        
    - Se probó sistemáticamente diferentes desplazamientos ROT (Caesar)
        
    - **ROT19** fue el desplazamiento correcto que produjo la flag legible
        
5. **Proceso de descifrado Caesar**:
    
    - Texto cifrado: `wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6}`
        
    - Aplicando ROT19:
        
        - `w` → `p`
            
        - `p` → `i`
            
        - `j` → `c`
            
        - `v` → `o`
            
        - `J` → `C`
            
        - `A` → `T`
            
        - `M` → `F`
            
        - `{` → `{`
            
        - `jhlzhy_k3jy9wa3k_i204hkj6` → `caesar_d3cr9pt3d_b204adc6`
            
        - `}` → `}`
            

**FLAG OBTENIDA:**  
`picoCTF{caesar_d3cr9pt3d_b204adc6}`

**NOTAS ADICIONALES:**

- La flag `caesar_d3cr9pt3d_b204adc6` describe perfectamente el proceso: "caesar decrypted b204adc6"
    
- Este reto demostró el concepto de **codificación en capas** (Base64 múltiple) seguido de **cifrado por sustitución** (Caesar)
    
- La combinación de Base64 doble con ROT19 creó un desafío interesante de múltiples etapas
    
- El uso de `b'...'` en la primera decodificación fue una pista importante de que se trataba de un string de Python bytes
    
- El reto enfatizó la importancia de examinar cuidadosamente los resultados intermedios en procesos de descifrado
    
- La técnica de prueba sistemática de desplazamientos ROT demostró ser efectiva para resolver cifrados Caesar sin conocer el desplazamiento
    
- La presencia de números y caracteres especiales (`3`, `9`, `_`, `{}`) que no se modifican en ROT ayudó a verificar el formato correcto
    
- Este ejercicio combinó habilidades de:
    
    - Manipulación de codificaciones (Base64)
        
    - Análisis criptográfico (identificación de patrones)
        
    - Programación básica (script para probar múltiples ROT)
        
    - Perseverancia en procesos multi-etapa
        
- El reto ilustró cómo técnicas criptográficas simples pueden combinarse para crear desafíos más complejos
    
- La flag final contenía una referencia hexadecimal `b204adc6` que podría ser un hash o identificador único del reto