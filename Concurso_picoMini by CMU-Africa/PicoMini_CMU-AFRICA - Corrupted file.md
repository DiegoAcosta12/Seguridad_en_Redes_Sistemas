### **RETO:** Corrupted file

**DESCRIPCIÓN:**  
This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life?

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Archivo presentado como JPEG pero no se podía abrir
        
    - Verificación del magic number del archivo
        
    - Los primeros bytes no correspondían al formato JPEG válido
        
2. **Proceso de resolución**:
    
    - Se examinó el archivo con editor hexadecimal
        
    - Se identificó que los primeros 4 bytes estaban incorrectos: `5C 78 FF E0`
        
    - Se comparó con el magic number correcto de JPEG: `FF D8 FF E0`
        
    - Se reparó el archivo reemplazando los primeros 4 bytes
        
    - Una vez reparado, la imagen se pudo abrir correctamente
        
3. **Descubrimiento clave**:
    
    - Magic number corrupto: `5C 78 FF E0`
        
    - Magic number correcto JPEG: `FF D8 FF E0`
        
    - La flag era visible en la imagen una vez reparada
        
    - Solo se necesitó corregir los primeros 4 bytes
        

**FLAG OBTENIDA:**  
`picoCTF{r3st0r1ng_th3_by73s_0e8fb0ec}`

**REFERENCIAS:**

- Herramienta: Editor hexadecimal
    
- Formato: JPEG (magic number: FF D8 FF E0)
    
- Técnica: Reparación de magic number de archivo
    
- Bytes corregidos: `5C 78 FF E0` → `FF D8 FF E0`