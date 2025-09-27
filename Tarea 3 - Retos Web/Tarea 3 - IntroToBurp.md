**RETO:**  
IntroToBurp

**DESCRIPCIÓN:**  
Try here to find the flag  
[http://titan.picoctf.net:64639](http://titan.picoctf.net:64639/)

**SOLUCIÓN:**

1. **Reconocimiento inicial**:
    
    - Identifiqué un formulario de registro con protección CSRF
        
    - La aplicación utilizaba Flask sessions
        
2. **Análisis con Burp Suite**:
    
    - Intercepté las requests HTTP utilizando Burp Suite
        
    - Identifiqué que el parámetro `debug` podía ser clave para obtener la flag
        
3. **Explotación exitosa**:
    
    - Probé diferentes valores para el parámetro `debug`
        
    - Descubrí que `debug=1` activaba el modo de depuración
        
    - La flag se mostró en la respuesta al enviar `POST /` con `debug=1`
        

**FLAG OBTENIDA:**  
`picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}`

**NOTAS ADICIONALES:**

- El reto demostró la importancia de probar diferentes valores de parámetros
    
- Burp Suite fue esencial para interceptar y modificar las requests HTTP
    
- El parámetro `debug` necesitaba el valor específico `1` para funcionar