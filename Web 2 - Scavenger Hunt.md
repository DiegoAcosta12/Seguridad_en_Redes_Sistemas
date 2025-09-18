**RETO:**  
Scavenger Hunt

**DESCRIPCIÓN:**  
There is some interesting information hidden around this site [http://mercury.picoctf.net:27278/](http://mercury.picoctf.net:27278/). Can you find it?  
You should have enough hints to find the files, don't run a brute forcer.

**SOLUCIÓN:**

1. **Código fuente de [index.html](https://index.html/)**:
    
    - Encontré un comentario con la primera parte de la flag: `picoCTF{t`.
        
2. **Archivo CSS (mycss.css)**:
    
    - Encontré un comentario con la segunda parte: `h4ts_4_l0`.
        
3. **Archivo robots.txt**:
    
    - Encontré un comentario con la tercera parte: `t_0f_pl4c`.
        
4. **Archivo .htaccess**:
    
    - Accedí a `http://mercury.picoctf.net:27278/.htaccess` y encontré un comentario con la cuarta parte: `3s_2_lO0k`.
        
5. **Archivo .DS_Store**:
    
    - Accedí a `http://mercury.picoctf.net:27278/.DS_Store` y usé el comando `strings` para extraer texto legible.
        
    - Encontré la quinta parte: `_a69684fd}`.
        
6. Uní todas las partes para formar la flag completa.
    

**FLAG OBTENIDA:**  
`picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_a69684fd}`

**NOTAS ADICIONALES:**

- El reto requirió revisar múltiples archivos ocultos y metadatos del sitio web (código fuente, CSS, robots.txt, .htaccess, .DS_Store).
    
- La pista en .htaccess sobre "Mac" y "Store" dirigió hacia el archivo .DS_Store, que es típico de macOS y a veces contiene información sensible.
    
- No se necesitó fuerza bruta, solo seguir las pistas en los archivos.
    

**REFERENCIAS:**

- [robots.txt](https://developers.google.com/search/docs/advanced/robots/intro)
    
- [.htaccess](https://httpd.apache.org/docs/current/howto/htaccess.html)
    
- [.DS_Store](https://en.wikipedia.org/wiki/.DS_Store)