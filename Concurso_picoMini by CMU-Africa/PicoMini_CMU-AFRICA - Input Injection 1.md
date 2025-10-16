### **RETO:** Input Injection 1

**DESCRIPCIÓN:**  
A friendly program wants to greet you… but its goodbye might say more than it should. Can you convince it to reveal the flag?

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Programa binario vulnerable descargado
        
    - Código fuente disponible (vuln.c)
        
    - Función `fun()` con buffers pequeños y uso de `strcpy()`
        
    - Ejecuta `system(c)` al final
        
2. **Proceso de resolución**:
    
    - Se identificó buffer overflow en la función `fun()`
        
    - Buffer `buffer[10]` podía desbordarse para sobrescribir `c[10]`
        
    - Como `c` se usa en `system(c)`, se podía inyectar comandos
        
    - Se usó payload: `'A' * 20 + ';cat flag.txt'`
        
    - Se conectó al servidor remoto con el payload
        
3. **Descubrimiento clave**:
    
    - Offset de 20 bytes para alcanzar y sobrescribir la variable `c`
        
    - El punto y coma (`;`) permitió ejecutar comandos adicionales
        
    - El desbordamiento permitió controlar qué comando ejecutaba `system()`
        

**FLAG OBTENIDA:**  
`picoCTF{0v3rfl0w_c0mm4nd_3185bc8f}`

**REFERENCIAS:**

- Servidor: `nc saffron-estate.picoctf.net 50428`
    
- Técnica: Buffer overflow + inyección de comandos
    
- Vulnerabilidad: `strcpy()` sin verificación de límites
    
- Payload: `python3 -c "print('A' * 20 + ';cat flag.txt')" | nc saffron-estate.picoctf.net 50428`
    
- Archivos: vuln, vuln.c