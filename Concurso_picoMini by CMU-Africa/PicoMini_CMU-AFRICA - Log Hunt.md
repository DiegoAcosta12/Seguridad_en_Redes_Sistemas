### **RETO:** Log Hunt

**DESCRIPCIÓN:**  
Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag from the fragments?

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Archivo de logs con fragmentos de la flag dispersos
        
    - Partes de la flag repetidas en diferentes lugares del log
        
    - Necesidad de reconstruir la flag completa
        
2. **Proceso de resolución**:
    
    - Se descargó y examinó el archivo de logs
        
    - Se identificaron todas las apariciones de fragmentos de flag
        
    - Se extrajeron las partes individuales de la flag
        
    - Se eliminaron duplicados y se ordenaron las partes
        
    - Se ensambló la flag completa uniendo todos los fragmentos
        
3. **Descubrimiento clave**:
    
    - La flag estaba dividida en múltiples partes dentro del log
        
    - Algunas partes aparecían repetidas en diferentes secciones
        
    - La reconstrucción requirió identificar el orden correcto
        
    - No se necesitaron herramientas especializadas, solo análisis manual
        

**FLAG OBTENIDA:**  
`picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}`

**REFERENCIAS:**

- Técnica: Análisis de logs y reconstrucción de datos
    
- Herramienta: Editor de texto/Bloc de notas
    
- Método: Búsqueda manual y ensamblaje de fragmentos
    
- Archivo: logs proporcionado en el reto