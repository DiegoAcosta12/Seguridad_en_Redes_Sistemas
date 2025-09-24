**RETO:**  
JaWT Scratchpad

**DESCRIPCIÓN:**  
Check the admin scratchpad! [https://jupiter.challenges.picoctf.org/problem/58210/](https://jupiter.challenges.picoctf.org/problem/58210/) or [http://jupiter.challenges.picoctf.org:58210](http://jupiter.challenges.picoctf.org:58210/)

**SOLUCIÓN:**

1. **Registro inicial**:
    
    - Me registré en el sitio usando el usuario "john" y recibí un JWT:  
        `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiam9obiJ9._fAF3H23ckP4QtF1Po3epuZWxmbwpI8Q26hRPDTh32Y`
        
2. **Análisis del JWT**:
    
    - Decodifiqué el JWT y confirmé que contenía `{"user":"john"}`
        
3. **Encontrar el secreto**:
    
    - Después de probar varios secretos comunes, descubrí que el secreto era **"ilovepico"**
        
4. **Crear JWT de admin**:
    
    - Generé un nuevo JWT con el payload `{"user":"admin"}` usando el secreto "ilovepico"
        
5. **Acceso al scratchpad del admin**:
    
    - Usé el JWT modificado para acceder como administrador y obtuve la flag
        

**FLAG OBTENIDA:**  
`picoCTF{jawt_was_just_what_you_thought_44c752f5}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de usar secretos fuertes en la firma de JWTs
    
- Secretos débiles como "ilovepico" permiten a atacantes generar tokens válidos
    
- La vulnerabilidad permitió escalar privilegios de usuario normal a administrador
    

**REFERENCIAS:**

- [JWT Security Best Practices](https://auth0.com/blog/a-look-at-the-latest-draft-for-jwt-bcp/)
    
- [JWT Attacks](https://portswigger.net/web-security/jwt)