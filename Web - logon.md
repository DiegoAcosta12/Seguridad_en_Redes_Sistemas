**RETO:**  
logon

**DESCRIPCIÓN:**  
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at?  
[https://jupiter.challenges.picoctf.org/problem/13594/](https://jupiter.challenges.picoctf.org/problem/13594/) (link) or [http://jupiter.challenges.picoctf.org:13594](http://jupiter.challenges.picoctf.org:13594/)

**SOLUCIÓN:**

1. Accedí al sitio web [http://jupiter.challenges.picoctf.org:13594](http://jupiter.challenges.picoctf.org:13594/).
    
2. Inspeccioné las cookies del sitio utilizando las herramientas de desarrollador (F12 → Application → Cookies).
    
3. Identifiqué una cookie llamada `admin` con valor `False`.
    
4. Modifiqué el valor de la cookie `admin` a `True` ejecutando en la consola JavaScript:
    
    javascript
    
    Copy
    
    Download
    
    document.cookie = "admin=True; path=/";
    
5. También aseguré que el usuario fuera `Joe` estableciendo una cookie adicional:
    
    javascript
    
    Copy
    
    Download
    
    document.cookie = "user=Joe; path=/";
    
6. Tras recargar la página, no se mostró cambios inmediatos, pero al acceder manualmente a la ruta `/flag` ([http://jupiter.challenges.picoctf.org:13594/flag](http://jupiter.challenges.picoctf.org:13594/flag)), se reveló la flag.
    

**FLAG OBTENIDA:**  
`picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}`

**NOTAS ADICIONALES:**

- La manipulación de cookies es una técnica común para escalar privilegios en aplicaciones web.
    
- Las cookies `admin` y `user` controlaban el acceso a contenido restringido.
    
- La flag no se mostró en la página principal, sino en una ruta específica (`/flag`).
    

**REFERENCIAS:**

- [HTTP Cookies (MDN)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)