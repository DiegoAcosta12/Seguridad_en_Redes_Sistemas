### **RETO:** Input Injection 2

**DESCRIPCIÓN:**  
This program greets you and then runs a command. But can you take control of what command it executes?

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Programa diferente al Input Injection 1 (hash MD5 diferente)
        
    - Código fuente muestra buffers en el heap: `username` y `shell`
        
    - `scanf("%s")` lee username sin límite de longitud
        
    - Ejecuta `system(shell)` donde `shell` inicialmente es `/bin/pwd`
        
2. **Proceso de resolución**:
    
    - Se identificó que `username` y `shell` están consecutivos en el heap
        
    - Diferencia de direcciones: 0x30 bytes (48 bytes)
        
    - Se desbordó `username` para sobrescribir `shell`
        
    - Se usó payload sin espacios (por `scanf("%s")`)
        
    - Comando exitoso: `cat<flag.txt` (sin espacios)
        
3. **Descubrimiento clave**:
    
    - Offset exacto: 48 bytes entre username y shell
        
    - `scanf("%s")` se detiene en espacios, necesitaba comando sin espacios
        
    - Redirección `<` funcionó para leer el archivo sin espacios
        
    - Payload: `'A' * 48 + 'cat<flag.txt'`
        

**FLAG OBTENIDA:**  
`picoCTF{us3rn4m3_2_sh3ll_7c9c7f0d}`

**REFERENCIAS:**

- Servidor: `nc saffron-estate.picoctf.net 62774`
    
- Técnica: Buffer overflow en heap + overwrite de variable
    
- Vulnerabilidad: `scanf("%s")` sin límite en buffers del heap
    
- Payload: `python3 -c "print('A' * 48 + 'cat<flag.txt')" | nc saffron-estate.picoctf.net 62774`
    
- Archivos: vuln2, vuln2.c