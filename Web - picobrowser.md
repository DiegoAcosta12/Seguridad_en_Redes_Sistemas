**RETO:**  
picobrowser

**DESCRIPCIÓN:**  
This website can be rendered only by picobrowser, go and catch the flag!  
[https://jupiter.challenges.picoctf.org/problem/28921/](https://jupiter.challenges.picoctf.org/problem/28921/) (link) or [http://jupiter.challenges.picoctf.org:28921](http://jupiter.challenges.picoctf.org:28921/)

**SOLUCIÓN:**

1. Accedí al sitio web [http://jupiter.challenges.picoctf.org:28921](http://jupiter.challenges.picoctf.org:28921/) y observé que requería un User-Agent específico llamado "picobrowser".
    
2. Utilicé el comando `curl` en la webshell de picoCTF para modificar el User-Agent en la solicitud HTTP:
    
    bash
    
    Copy
    
    Download
    
    curl -H "User-Agent: picobrowser" http://jupiter.challenges.picoctf.org:28921/
    
3. La respuesta HTML mostró un botón que llevaba a la ruta `/flag`.
    
4. Ejecuté otro comando `curl` para acceder a `/flag` con el mismo User-Agent modificado:
    
    bash
    
    Copy
    
    Download
    
    curl -H "User-Agent: picobrowser" http://jupiter.challenges.picoctf.org:28921/flag
    
5. El servidor respondió con la flag incrustada en el HTML: `picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}`.
    

**FLAG OBTENIDA:**  
`picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}`

**NOTAS ADICIONALES:**

- El servidor validaba el header `User-Agent` para restringir el acceso.
    
- Herramientas como `curl` permiten modificar headers HTTP fácilmente para impersonar clientes específicos.
    
- Este reto demuestra la importancia de la validación del lado del servidor y cómo los headers pueden ser manipulados.
    

**REFERENCIAS:**

- [HTTP Headers (MDN)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)