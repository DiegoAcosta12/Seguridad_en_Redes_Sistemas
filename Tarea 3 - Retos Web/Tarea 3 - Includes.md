**RETO:**  
Includes

**DESCRIPCIÓN:**  
Can you get the flag? Go to this website and see what you can discover.  
[http://saturn.picoctf.net:51145](http://saturn.picoctf.net:51145/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Accedí al sitio web y revisé el código fuente HTML
        
    - Identifiqué que la página incluía dos archivos externos: `style.css` y `script.js`
        
    - El título del reto "Includes" sugería que la flag estaría en los archivos incluidos
        
2. **Análisis de archivos incluidos**:
    
    - Descargué y revisé el archivo `style.css`
        
    - Encontré un comentario CSS con la primera parte de la flag: `picoCTF{1nclu51v17y_1of2_`
        
    - Descargué y revisé el archivo `script.js`
        
    - Encontré un comentario JavaScript con la segunda parte: `f7w_2of2_df589022}`
        
3. **Reconstrucción de la flag**:
    
    - Combiné ambas partes para formar la flag completa
        
    - La primera parte estaba en el archivo CSS y la segunda en el archivo JavaScript
        

**FLAG OBTENIDA:**  
`picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}`

**NOTAS ADICIONALES:**

- Este reto demostró la importancia de revisar todos los recursos incluidos en una página web
    
- Los archivos CSS y JavaScript pueden contener información sensible en comentarios
    
- La flag estaba dividida intencionalmente entre dos archivos para enfatizar el concepto de "includes"
    
- No se requirieron herramientas especializadas, solo inspección básica del código fuente