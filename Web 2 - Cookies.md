**RETO:**  
Cookies

**DESCRIPCIÓN:**  
Who doesn't love cookies? Try to figure out the best one.  
[http://mercury.picoctf.net:27177/](http://mercury.picoctf.net:27177/)

**SOLUCIÓN:**

1. Accedí al sitio web y observé que se establecía una cookie llamada `name` con un valor inicial (por ejemplo, `-1`).
    
2. Usando las **Herramientas de Desarrollo** del navegador (pestaña Application o Almacenamiento), modifiqué manualmente el valor de la cookie `name` a diferentes números (probando valores como 0, 1, 2, ...).
    
3. Al cambiar el valor de la cookie a **18**, la página mostró la flag en lugar del mensaje habitual.
    
4. Confirmé la solución usando **curl** desde la terminal:
    
    bash
    
    Copy
    
    Download
    
    curl -b "name=18" http://mercury.picoctf.net:27177/
    
    El resultado incluyó la flag en el HTML de respuesta.
    

**FLAG OBTENIDA:**  
`picoCTF{3v3ry1_l0v3s_c00k135_064663be}`

**NOTAS ADICIONALES:**

- Las cookies HTTP son utilizadas por los servidores para almacenar información en el cliente.
    
- Modificar cookies manualmente es una técnica común en pruebas de penetración para bypassear restricciones o acceder a datos ocultos.
    
- El valor `18` fue el "mejor" cookie (the best one) según la lógica del servidor.
    

**REFERENCIAS:**

- [HTTP Cookies (MDN Web Docs)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
    
- [Using curl with cookies](https://curl.se/docs/manpage.html#-b)