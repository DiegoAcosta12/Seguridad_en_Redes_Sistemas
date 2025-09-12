**RETO:**  
dont-use-client-side

**DESCRIPCIÓN:**  
Can you break into this super secure portal?  
[https://jupiter.challenges.picoctf.org/problem/17682/](https://jupiter.challenges.picoctf.org/problem/17682/) (link) or [http://jupiter.challenges.picoctf.org:17682](http://jupiter.challenges.picoctf.org:17682/)

**SOLUCIÓN:**

1. Accedí al sitio web [http://jupiter.challenges.picoctf.org:17682](http://jupiter.challenges.picoctf.org:17682/).
    
2. Inspeccioné el código fuente de la página (clic derecho → "Ver código fuente").
    
3. Encontré una función JavaScript llamada `verify()` que validaba la contraseña ingresada en el cliente.
    
4. La función dividía la contraseña en 8 partes y comparaba cada segmento con valores específicos:
    
    - `0-4`: 'pico'
        
    - `4-8`: 'CTF{'
        
    - `8-12`: 'no_c'
        
    - `12-16`: 'lien'
        
    - `16-20`: 'ts_p'
        
    - `20-24`: 'lz_b'
        
    - `24-28`: '706c' (hexadecimal para "pl")
        
    - `28-30`: '5}'
        
5. Reconstruí la contraseña concatenando las partes en orden:  
    `pico` + `CTF{` + `no_c` + `lien` + `ts_p` + `lz_b` + `706c` + `5}` = `picoCTF{no_clients_plz_b706c5}`
    
6. La contraseña reconstruida es la flag itself.
    

**FLAG OBTENIDA:**  
`picoCTF{no_clients_plz_b706c5}`

**NOTAS ADICIONALES:**

- El reto demuestra los riesgos de realizar validaciones críticas (como contraseñas) en el lado del cliente, ya que los atacantes pueden inspeccionar y manipular el código.
    
- La flag se obtiene directamente al reconstruir la contraseña a partir de las condiciones en el JavaScript.
    

**REFERENCIAS:**

- [Client-Side Security](https://owasp.org/www-community/controls/Client_Side_Security)