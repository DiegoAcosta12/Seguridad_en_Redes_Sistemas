**RETO:**  
More SQLi

**DESCRIPCIÓN:**  
Can you find the flag on this website. Try to find the flag here.  
[http://saturn.picoctf.net:53303](http://saturn.picoctf.net:53303/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Accedí al sitio y encontré un formulario de login con campos para username y password.
        
    - El sitio mostraba en la respuesta la consulta SQL ejecutada, lo que ayudó a entender la estructura de la query.
        
2. **Análisis de la vulnerabilidad**:
    
    - La consulta SQL era: `SELECT id FROM users WHERE password = '[password]' AND username = '[username]'`
        
    - Identifiqué que ambos campos (username y password) eran vulnerables a SQL Injection.
        
3. **Explotación exitosa**:
    
    - Probé varias inyecciones SQL y descubrí que la siguiente funcionaba:
        
        text
        
        Copy
        
        Download
        
        Username: admin
        Password: ' OR '1'='1
        
    - Esta inyección transformó la consulta en:
        
        sql
        
        Copy
        
        Download
        
        SELECT id FROM users WHERE password = '' OR '1'='1' AND username = 'admin'
        
    - La condición `'1'='1'` siempre es verdadera, bypasseando la autenticación.
        
4. **Obtención de la flag**:
    
    - Después del login exitoso, la flag se mostró en la página de respuesta.
        

**FLAG OBTENIDA:**  
`picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8ee9477}`

**NOTAS ADICIONALES:**

- Este reto demostró la importancia de sanitizar **todos** los campos de entrada, no solo el username.
    
- La técnica `' OR '1'='1` es clásica pero efectiva cuando no hay sanitización adecuada.
    
- El hecho de que el sitio mostrara la consulta SQL ayudó enormemente en el debugging del ataque.
    

**REFERENCIAS:**

- [SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection)
    
- [SQL Injection Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)