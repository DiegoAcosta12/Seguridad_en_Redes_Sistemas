**RETO:**  
where are the robots

**DESCRIPCIÓN:**  
Can you find the robots?  
[https://jupiter.challenges.picoctf.org/problem/60915/](https://jupiter.challenges.picoctf.org/problem/60915/) (link) or [http://jupiter.challenges.picoctf.org:60915](http://jupiter.challenges.picoctf.org:60915/)

**SOLUCIÓN:**

1. Accedí al sitio web y revisé el archivo `robots.txt` en:  
    [http://jupiter.challenges.picoctf.org:60915/robots.txt](http://jupiter.challenges.picoctf.org:60915/robots.txt)
    
    - Encontré la entrada: `Disallow: /8028f.html`
        
2. Navegué a la página prohibida:  
    [http://jupiter.challenges.picoctf.org:60915/8028f.html](http://jupiter.challenges.picoctf.org:60915/8028f.html)
    
3. La flag estaba visible en la página:  
    `picoCTF{ca1cu1at1ng_Mach1n3s_8028f}`
    

**FLAG OBTENIDA:**  
`picoCTF{ca1cu1at1ng_Mach1n3s_8028f}`

**NOTAS ADICIONALES:**

- El archivo `robots.txt` es un estándar web que controla el acceso de los rastreadores (bots) a ciertas partes del sitio.
    
- Los retos de CTF a menudo esconden flags en rutas restringidas por `robots.txt`.
    

**REFERENCIAS:**

- [robots.txt Explained](https://developers.google.com/search/docs/advanced/robots/intro)