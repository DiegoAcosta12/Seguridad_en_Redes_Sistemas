**RETO:**  
Unminify

**DESCRIPCIÓN:**  
I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!  
Browse here, and find the flag!  
[http://titan.picoctf.net:55745](http://titan.picoctf.net:55745/)

**SOLUCIÓN:**

1. **Análisis del sitio web**:
    
    - El código HTML estaba minificado (todo en una línea sin formato)
        
    - La página afirmaba que el navegador había recibido la flag
        
2. **Búsqueda de la flag**:
    
    - Utilicé el comando `grep` para buscar patrones como "pico", "flag" y "ctf"
        
    - Encontré la flag directamente en el atributo `class` de una etiqueta `<p>`
        
3. **Hallazgo de la flag**:
    
    - La flag estaba en: `<p class="picoCTF{pr3tty_c0d3_b99eb82e}"></p>`
        
    - Estaba visible pero oculta en el código minificado
        

**FLAG OBTENIDA:**  
`picoCTF{pr3tty_c0d3_b99eb82e}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de revisar el código fuente minificado
    
- La flag hacía referencia a "pretty code" (pr3tty_c0d3)
    
- Aunque el código estaba comprimido, la información seguía siendo accesible