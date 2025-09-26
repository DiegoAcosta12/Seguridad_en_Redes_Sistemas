**RETO:** MatchTheRegex

**DESCRIPCIÓN:**  
How about trying to match a regular expression. The website is running here: [http://saturn.picoctf.net:54680](http://saturn.picoctf.net:54680/)

**SOLUCIÓN:**

1. **Acceso inicial**:
    
    - Accedí al sitio web en [http://saturn.picoctf.net:54680](http://saturn.picoctf.net:54680/)
        
    - Identifiqué un campo de entrada de texto con un botón de envío
        
2. **Análisis del código fuente**:
    
    - Inspeccioné el código HTML de la página
        
    - Encontré un comentario crítico: `<!-- How about: picoCTF{[0-9a-f_]*} -->`
        
    - Este comentario revelaba la expresión regular que debía coincidir
        
3. **Comprensión del regex**:
    
    - Analicé el patrón: `picoCTF{[0-9a-f_]*}`
        
    - El regex permite:
        
        - Texto literal "picoCTF{"
            
        - Cualquier combinación de caracteres hexadecimales (0-9, a-f) y guiones bajos
            
        - Cierre con "}"
            
4. **Generación de input válido**:
    
    - Creé un texto que coincidiera con el patrón: `picoCTF{abcdef0123456789_}`
        
    - Este input satisfacía todos los requisitos del regex
        
5. **Obtención de la flag**:
    
    - Envié el texto mediante el formulario web
        
    - El sistema validó que coincidía con el regex y mostró la flag real
        

**FLAG OBTENIDA:**  
`picoCTF{succ3ssfully_matchtheregex_f89ea585}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de revisar el código fuente de aplicaciones web
    
- Los comentarios en HTML pueden contener información sensible o pistas críticas
    
- La expresión regular era permisiva pero requería el formato específico de flag de PicoCTF
    
- Cualquier texto que siguiera el patrón `picoCTF{[0-9a-f_]*}` habría funcionado
    

**CONCEPTOS CLAVE:**

- Expresiones regulares (regex)
    
- Inspección de código fuente web
    
- Validación de entrada en aplicaciones web
    
- Seguridad through obscurity (no es un método seguro)
    

**REFERENCIAS:**

- [MDN Web Docs - Expresiones Regulares](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_Expressions)
    
- [OWASP - Client Side Storage](https://owasp.org/www-community/vulnerabilities/Client-side_Storage)