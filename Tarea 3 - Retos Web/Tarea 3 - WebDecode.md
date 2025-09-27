**RETO:**  
WebDecode

**DESCRIPCIÓN:**  
Do you know how to use the web inspector? Start searching here to find the flag  
[http://titan.picoctf.net:49955](http://titan.picoctf.net:49955/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Identifiqué múltiples páginas: `index.html`, `about.html`, `contact.html`
        
    - El mensaje "Keep Navigating" sugería explorar más allá de la página principal
        
2. **Análisis con inspector web**:
    
    - Revisé el código fuente de `about.html` utilizando el inspector del navegador
        
    - Encontré un atributo oculto en una etiqueta `<section>`: `notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMWY4MzI2MTV9"`
        
3. **Decodificación de la flag**:
    
    - Identifiqué que el valor del atributo estaba codificado en Base64
        
    - Decodifiqué la string obteniendo la flag: `picoCTF{web_succ3ssfully_d3c0ded_1f832615}`
        

**FLAG OBTENIDA:**  
`picoCTF{web_succ3ssfully_d3c0ded_1f832615}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de revisar todos los atributos HTML, no solo el contenido visible
    
- La codificación Base64 es común para ocultar información en páginas web
    
- La flag hace referencia a "web successfully decoded"