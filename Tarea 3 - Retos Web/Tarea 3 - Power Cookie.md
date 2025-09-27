**RETO:**  
Power Cookie

**DESCRIPCIÓN:**  
Can you get the flag? Go to this website and see what you can discover.  
[http://saturn.picoctf.net:64790](http://saturn.picoctf.net:64790/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Identifiqué una página con un botón "Continue as guest"
        
    - Analicé el archivo `guest.js` que se cargaba en la página
        
2. **Análisis de la vulnerabilidad**:
    
    - Descubrí que `guest.js` establecía una cookie `isAdmin=0`
        
    - La aplicación redirigía a `check.php` después de establecer la cookie
        
3. **Explotación de la cookie**:
    
    - Modifiqué la cookie `isAdmin` cambiando su valor de `0` a `1`
        
    - Accedí directamente a `check.php` con la cookie modificada
        
    - La aplicación aceptó el valor y mostró la flag
        

**FLAG OBTENIDA:**  
`picoCTF{gr4d3_A_c00k13_0d351e23}`

**NOTAS ADICIONALES:**

- El reto demostró cómo las cookies pueden controlar el acceso a funcionalidades
    
- La validación de permisos en el lado del cliente es insegura
    
- La flag hace referencia a "grade A cookie" (gr4d3_A_c00k13)