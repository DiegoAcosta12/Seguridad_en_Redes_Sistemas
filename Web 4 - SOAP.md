**RETO:** SOAP

**DESCRIPCIÓN:**  
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?  
Web Portal: [http://saturn.picoctf.net:64904](http://saturn.picoctf.net:64904/)

**SOLUCIÓN:**

1. **Reconocimiento del objetivo**:
    
    - Accedí al sitio web en [http://saturn.picoctf.net:64904](http://saturn.picoctf.net:64904/)
        
    - La página mostraba contenido estático sobre instituciones educativas
        
    - No había formularios visibles ni funcionalidades aparentes
        
2. **Descubrimiento del endpoint vulnerable**:
    
    - Mediante Burp Suite, descubrí un endpoint oculto: `/data`
        
    - Este endpoint aceptaba requests POST con contenido XML
        
    - El servicio procesaba XML sin validación adecuada
        
3. **Explotación de vulnerabilidad XXE**:
    
    - Construí un payload XML malicioso con entidad externa:
        
    
    xml
    
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE foo [
    <!ENTITY xxe SYSTEM "file:///etc/passwd">
    ]>
    <data>
    <ID>&xxe;</ID>
    </data>
    
    - La entidad externa apuntaba a `file:///etc/passwd`
        
4. **Ejecución del ataque**:
    
    - Envié el payload XML mediante POST a `/data`
        
    - El servidor procesó la entidad externa y devolvió el contenido de `/etc/passwd`
        
    - La flag estaba incluida en la respuesta del servidor
        

**FLAG OBTENIDA:**  
`picoCTF{XML_3xtern@l_3nt1t1ty_55662c16}`

**VULNERABILIDAD IDENTIFICADA:**

- **CWE-611: Improper Restriction of XML External Entity Reference**
    
- El servicio procesaba XML sin restringir entidades externas
    
- Permitía la inclusión de archivos locales del sistema
    

**IMPACTO:**

- Lectura de archivos arbitrarios del sistema (Local File Inclusion)
    
- Posible escalada a Remote Code Execution en configuraciones específicas
    

**RECOMENDACIONES DE SEGURIDAD:**

1. Deshabilitar el procesamiento de entidades externas en el parser XML
    
2. Implementar listas blancas de elementos y atributos permitidos
    
3. Validar y sanitizar toda entrada XML antes del procesamiento
    
4. Usar formatos de datos más seguros como JSON cuando sea posible
    

**HERRAMIENTAS UTILIZADAS:**

- Burp Suite (para interceptación y envío de requests)
    
- Manual XML crafting (para el payload XXE)
    

**CONCEPTOS CLAVE:**

- XML External Entity (XXE) Injection
    
- Local File Inclusion (LFI)
    
- Web Service Security
    
- Input Validation
    

**REFERENCIAS:**

- [OWASP XXE Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html)
    
- [PortSwigger XXE Attacks](https://portswigger.net/web-security/xxe)