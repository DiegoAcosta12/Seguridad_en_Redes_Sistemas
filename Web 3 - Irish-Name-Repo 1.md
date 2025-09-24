**RETO:**  
Irish-Name-Repo 1

**DESCRIPCIÓN:**  
There is a website running at [https://jupiter.challenges.picoctf.org/problem/50009/](https://jupiter.challenges.picoctf.org/problem/50009/) (link) or [http://jupiter.challenges.picoctf.org:50009](http://jupiter.challenges.picoctf.org:50009/). Do you think you can log us in? Try to see if you can login!

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Accedí al sitio y exploré las secciones disponibles (Home, Support, Admin Login).
        
    - Identifiqué que el objetivo era bypassear la autenticación en el panel "Admin Login".
        
2. **Análisis de vulnerabilidad**:
    
    - El formulario de login era susceptible a **SQL Injection**, una vulnerabilidad común cuando las entradas del usuario no están sanitizadas.
        
    - Probé varias técnicas de inyección SQL para bypassear la autenticación.
        
3. **Explotación exitosa**:
    
    - Usé la siguiente inyección en el campo de username:
        
        text
        
        Copy
        
        Download
        
        Username: admin' --
        Password: [vacío]
        
    - El comentario `--` anuló la verificación de password, permitiendo el acceso como administrador.
        
4. **Obtención de la flag**:
    
    - Después del login exitoso, la flag se mostró directamente en la página.
        

**FLAG OBTENIDA:**  
`picoCTF{s0m3_SQL_fb3fe2ad}`

**NOTAS ADICIONALES:**

- La inyección SQL `admin' --` funciona porque probablemente la consulta original es similar a:
    
    sql
    
    Copy
    
    Download
    
    SELECT * FROM users WHERE username = 'admin' AND password = 'password'
    
- Al usar `admin' --`, la consulta se convierte en:
    
    sql
    
    Copy
    
    Download
    
    SELECT * FROM users WHERE username = 'admin' --' AND password = 'password'
    
- Esto comenta el resto de la consulta, evitando la verificación de password.
    

**REFERENCIAS:**

- [SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection)
    
- [SQL Injection Prevention](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)