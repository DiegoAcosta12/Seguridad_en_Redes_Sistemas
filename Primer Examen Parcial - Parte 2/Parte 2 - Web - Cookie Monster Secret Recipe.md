**RETO:**  
Cookie Monster Secret Recipe

**DESCRIPCIÓN:**  
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?  
[http://verbal-sleep.picoctf.net:55571/](http://verbal-sleep.picoctf.net:55571/)

**SOLUCIÓN:**

1. **Análisis inicial del sitio web**:
    
    - Accedí al sitio web proporcionado que mostraba un formulario de login
        
    - El formulario enviaba credenciales a `login.php` mediante método POST
        
    - El mensaje del sitio indicaba: "Cookie Monster's Secret Recipe"
        
2. **Investigación del endpoint de login**:
    
    - Envié una solicitud POST a `login.php` con credenciales arbitrarias:
        
        bash
        
        curl -X POST http://verbal-sleep.picoctf.net:55571/login.php \
          -d "username=admin&password=admin" -v
        
    - El servidor respondió con "Access Denied" pero estableció una cookie importante
        
    - El mensaje de error contenía una pista clave: _"Me no need password. Me just need cookies!"_
        
3. **Descubrimiento y análisis de la cookie**:
    
    - Identifiqué que el servidor establecía la cookie: `secret_recipe`
        
    - Valor de la cookie: `cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzX0E2RkEwN0Q4fQ%3D%3D`
        
    - La cookie estaba codificada en Base64 con URL-encoding
        
4. **Decodificación de la flag**:
    
    - Realicé URL-decoding (convertí `%3D` a `=`)
        
    - Apliqué decodificación Base64 al resultado:
        
        bash
        
        echo "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzX0E2RkEwN0Q4fQ==" | base64 -d
        

**FLAG OBTENIDA:**  
`picoCTF{c00k1e_m0nster_l0ves_c00kies_A6FA07D8}`

**NOTAS ADICIONALES:**

- La flag `c00k1e_m0nster_l0ves_c00kies` hace referencia directa al tema del reto sobre el Cookie Monster y las galletas
    
- Este reto demuestra la importancia de revisar todas las respuestas del servidor, incluyendo headers y cookies, incluso en respuestas de error
    
- La cookie se establecía independientemente de las credenciales proporcionadas, lo que indica que el mecanismo de autenticación era irrelevante
    
- La codificación Base64 es comúnmente utilizada para almacenar datos en cookies HTTP
    
- El reto enfatiza el principio de "never trust client-side data" y la importancia de revisar toda la comunicación HTTP
