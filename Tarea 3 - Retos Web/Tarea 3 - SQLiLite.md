**RETO:**  
SQLiLite

**DESCRIPCIÓN:**  
Can you login to this website? Try to login here.  
[http://saturn.picoctf.net:53490](http://saturn.picoctf.net:53490/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Identifiqué un formulario de login que enviaba a `login.php`
        
    - Los campos eran `username`, `password` y `debug=0` (oculto)
        
2. **Explotación de SQL Injection**:
    
    - Probé el payload `admin' OR 1=1--` en el campo username
        
    - La inyección bypassó la autenticación y permitió el login
        
    - La aplicación mostró un mensaje de éxito con la flag oculta en un tag `<p hidden>`
        
3. **Obtención de la flag**:
    
    - La flag estaba visible en el código HTML de la respuesta
        
    - Se mostró el mensaje: "Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}"
        

**FLAG OBTENIDA:**  
`picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}`

**NOTAS ADICIONALES:**

- El reto demostró una vulnerabilidad clásica de SQL Injection
    
- El parámetro `debug` ayudó a ver la consulta SQL ejecutada
    
- La validación de entrada era insuficiente, permitiendo la inyección