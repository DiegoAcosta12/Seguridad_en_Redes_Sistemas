**RETO:**  
Secrets

**DESCRIPCIÓN:**  
We have several pages hidden. Can you find the one with the flag?  
[http://saturn.picoctf.net:56899](http://saturn.picoctf.net:56899/)

**SOLUCIÓN:**

1. **Reconocimiento inicial**:
    
    - Identifiqué referencias al directorio `secret/` en el código fuente de la página principal
        
    - El archivo CSS estaba en `secret/assets/index.css`
        
2. **Exploración de directorios ocultos**:
    
    - Accedí a `/secret/` y encontré un mensaje indicando que estaba cerca
        
    - Descubrí el directorio `/secret/hidden/` que contenía un formulario de login
        
    - El formulario mencionaba el directorio `superhidden/`
        
3. **Descubrimiento de la flag**:
    
    - Accedí a `/secret/hidden/superhidden/`
        
    - Encontré la flag directamente en el código HTML de la página
        

**FLAG OBTENIDA:**  
`picoCTF{succ3ss_@h3n1c@10n_790d2615}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de la enumeración de directorios
    
- Las rutas ocultas pueden ser descubiertas analizando referencias en el código fuente
    
- La flag hace referencia a "success authentication"