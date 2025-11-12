**RETO:** Safe Opener 2

**DESCRIPCION:**  
What can you do with this file? I forgot the key to my safe but this file is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

**SOLUCION:**

- Descargué el archivo SafeOpener.class que contenía el bytecode compilado de Java
    
- Usé la herramienta `javap -c` para desensamblar el bytecode y ver las instrucciones
    
- Analicé el código desensamblado y encontré que la función `openSafe` contenía la flag hardcodeada directamente
    
- La flag estaba visible como un string constante en el bytecode: `picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}`
    

**Proceso de solución:**

1. **Descargar el archivo:**
    
    bash
    
    wget https://artifacts.picoctf.net/c/292/SafeOpener.class
    
2. **Desensamblar el bytecode:**
    
    bash
    
    javap -c SafeOpener
    
3. **Analizar la función openSafe:**
    
    - En la línea `0: ldc #24` se carga la string constante con la flag
        
    - La flag estaba visible directamente en el output: `picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}`
        

**Flag:** `picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}`

**NOTAS:**

- El reto demostró que incluso los archivos compilados pueden revelar información sensible
    
- Los strings hardcodeados en Java se almacenan en la constant pool del .class file y son fácilmente accesibles
    
- Herramientas como `javap` pueden desensamblar bytecode de Java sin necesidad de decompiladores complejos
    
- La flag "SAf3_0p3n3rr_y0u_solv3d_it_0e57c117" significa "Safe opener you solved it" en leet speak
    
- Nunca se debe hardcodear información sensible en aplicaciones, incluso si están compiladas
    
- El bytecode de Java mantiene mucha información del código original, incluyendo nombres de métodos y strings literales
    
- Este reto fue más fácil que el anterior ya que la flag estaba visible directamente sin necesidad de codificación