### **RETO:** Crack the Gate 2

**DESCRIPCIÓN:**  
The login system has been upgraded with a basic rate-limiting mechanism that locks out repeated failed attempts from the same source. We’ve received a tip that the system might still trust user-controlled headers. Your objective is to bypass the rate-limiting restriction and log in using the known email address: [ctf-player@picoctf.org](https://mailto:ctf-player@picoctf.org/) and uncover the hidden secret.

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Sitio web con rate-limiting en: [http://amiable-citadel.picoctf.net:53992](http://amiable-citadel.picoctf.net:53992/)
        
    - Sistema bloquea intentos fallidos desde la misma IP
        
    - Lista de contraseñas proporcionada
        
2. **Proceso de resolución**:
    
    - Se identificó que el sistema confía en el header `X-Forwarded-For`
        
    - Se creó un script para probar cada contraseña con una IP diferente
        
    - Se rotaron IPs ficticias usando `X-Forwarded-For: 192.168.1.X`
        
    - Se probaron sistemáticamente todas las contraseñas de la lista
        
3. **Descubrimiento clave**:
    
    - La contraseña correcta era: `X68f2Ftm`
        
    - El header `X-Forwarded-For` permitió bypass del rate-limiting
        
    - Cada intento usó una IP diferente evitando el bloqueo
        

**FLAG OBTENIDA:**  
`picoCTF{xff_byp4ss_brut3_3477bf15}`

**REFERENCIAS:**

- URL: [http://amiable-citadel.picoctf.net:53992](http://amiable-citadel.picoctf.net:53992/)
    
- Técnica: Bypass de rate-limiting via header X-Forwarded-For
    
- Herramienta: `curl`, script bash
    
- Contraseñas probadas: 20 en total
    
- Comando script: Rotación de IPs con `X-Forwarded-For: 192.168.1.$counter`