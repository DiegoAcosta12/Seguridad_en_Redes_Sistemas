### **RETO:** Crack the Gate 1

**DESCRIPCIÓN:**  
We’re in the middle of an investigation. One of our persons of interest, ctf player, is believed to be hiding sensitive data inside a restricted web portal. We’ve uncovered the email address he uses to log in: [ctf-player@picoctf.org](https://mailto:ctf-player@picoctf.org/). Unfortunately, we don’t know the password, and the usual guessing techniques haven’t worked. But something feels off... it’s almost like the developer left a secret way in. Can you figure it out?

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Sitio web de login en: [http://amiable-citadel.picoctf.net:59876](http://amiable-citadel.picoctf.net:59876/)
        
    - Credenciales conocidas: [ctf-player@picoctf.org](https://mailto:ctf-player@picoctf.org/)
        
    - Contraseña desconocida
        
2. **Proceso de resolución**:
    
    - Se examinó el código fuente de la página de login
        
    - Se encontró un comentario codificado en ROT13: `<!-- ABGR: Wnpx - grzcbenel olcnff: hfr urnqre "K-Qri-Npprff: lrf" -->`
        
    - Se decodificó el ROT13 revelando: `Jack - temporary bypass: use header "X-Dev-Access: yes"`
        
    - Se utilizó el header especial en la petición POST al endpoint /login
        
3. **Descubrimiento clave**:
    
    - El comentario en el código fuente contenía un bypass de autenticación
        
    - El header `X-Dev-Access: yes` permitía omitir la verificación de credenciales
        
    - La flag se obtenía directamente al usar este header
        

**FLAG OBTENIDA:**  
`picoCTF{brut4_f0rc4_3c6b118b}`

**REFERENCIAS:**

- URL: [http://amiable-citadel.picoctf.net:59876](http://amiable-citadel.picoctf.net:59876/)
    
- Técnica: Bypass de autenticación via headers HTTP
    
- Herramienta: `curl`
    
- Comando: `curl -X POST http://amiable-citadel.picoctf.net:59876/login -H "Content-Type: application/json" -H "X-Dev-Access: yes" -d '{"email":"ctf-player@picoctf.org","password":"anypassword"}'`
    
- Técnica: Decodificación ROT13