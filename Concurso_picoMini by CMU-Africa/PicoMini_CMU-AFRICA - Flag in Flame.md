### **RETO:** Flag in Flame

**DESCRIPCIÓN:**  
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it.

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Archivo logs.txt con datos codificados en Base64
        
    - Datos muy extensos, no logs típicos
        
    - Sospecha de archivo oculto dentro del Base64
        
2. **Proceso de resolución**:
    
    - Se decodificó el Base64 completo del archivo logs.txt
        
    - La decodificación generó una imagen PNG
        
    - La imagen contenía texto en hexadecimal visible
        
    - Se identificó y corrigió un byte erróneo en el hexadecimal
        
    - Se decodificó el hexadecimal a texto ASCII
        
3. **Descubrimiento clave**:
    
    - Base64 → PNG con hexadecimal
        
    - Hexadecimal corregido: `f4` → `6f` para hacerlo válido
        
    - Secuencia hexadecimal: `7069636f4354467B...` decodifica a `picoCTF{...`
        
    - La flag estaba codificada en dos capas (Base64 + Hex)
        

**FLAG OBTENIDA:**  
`picoCTF{forensics_analysis_is_amazing_ac1e3584}`

**REFERENCIAS:**

- Codificaciones: Base64 → PNG → Hexadecimal → ASCII
    
- Herramientas: Decodificador Base64, visor de imágenes, decodificador hexadecimal
    
- Corrección: Byte `f4` cambiado a `6f` en el hexadecimal
    
- Técnica: Análisis forense de datos encadenados