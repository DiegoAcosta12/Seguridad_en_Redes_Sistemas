**RETO:**  
Most Cookies

**DESCRIPCIÓN:**  
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!  
Web Portal: [http://mercury.picoctf.net:35697/](http://mercury.picoctf.net:35697/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Accedí al sitio y analicé el código fuente del servidor (server.py)
        
    - Identifiqué que la aplicación usaba Flask sessions con una secret key aleatoria
        
    - La lista de posibles secret keys eran nombres de galletas: `cookie_names`
        
    - Para obtener la flag, se necesitaba `session['very_auth'] = 'admin'`
        
2. **Análisis de la vulnerabilidad**:
    
    - La cookie de sesión actual era: `eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aNcsxg.P6l3sa75ocDgiO6vrPDSLpW53Bw`
        
    - Al decodificarla, contenía: `{'very_auth': 'blank'}`
        
    - La vulnerabilidad consistía en que la secret key era predecible (de una lista fija)
        
3. **Ataque de fuerza bruta a la secret key**:
    
    - Creé un script Python que probaba cada nombre de galleta como secret key
        
    - El script intentaba decodificar la cookie con cada key posible
        
    - La key correcta encontrada fue: **`peanut butter`**
        
4. **Creación de cookie de administrador**:
    
    - Una vez obtenida la secret key, generé una nueva cookie de sesión
        
    - Establecí `session['very_auth'] = 'admin'`
        
    - La nueva cookie generada fue: `eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aNcuwg.nbZU4QPDdrozHp2_Qmc19gENuOU`
        
5. **Obtención de la flag**:
    
    - Reemplacé la cookie en el navegador usando Developer Tools
        
    - Accedí a la ruta `/display` con la sesión de administrador
        
    - La flag se mostró en la página
        

**FLAG OBTENIDA:**  
`picoCTF{pwn_4ll_th3_cook1E5_22fe0842}`

**NOTAS ADICIONALES:**

- Este reto demostró la importancia de usar secret keys **realmente aleatorias** y no predecibles
    
- Las cookies de Flask sessions son seguras solo si la secret key es robusta
    
- La técnica de cookie cracking es efectiva cuando las keys son débiles o predecibles
    
- El nombre "Most Cookies" era una pista sobre la naturaleza de la lista de secret keys
    

**REFERENCIAS:**

- [Flask Session Security](https://flask.palletsprojects.com/en/stable/security/#session-security)
    
- [Flask Session Cookie Manipulation](https://blog.paradoxis.nl/defeating-flasks-session-management-65706ba9d3ce)
    
- [OWASP Session Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html)