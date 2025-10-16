### **RETO:** Riddle Registry

**DESCRIPCIÓN:**  
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - PDF aparentemente con contenido sin sentido
        
    - Sospecha de información oculta en metadatos
        
    - Necesidad de examinar metadatos del documento
        
2. **Proceso de resolución**:
    
    - Se utilizó `exiftool` para extraer metadatos del PDF
        
    - Se identificó el campo "Author" con datos sospechosos
        
    - Los datos en el campo Author estaban codificados en Base64
        
    - Se decodificó el Base64 para revelar la flag
        
3. **Descubrimiento clave**:
    
    - La flag estaba oculta en los metadatos del PDF
        
    - Específicamente en el campo "Author"
        
    - Codificada en Base64 para ocultarla
        
    - No era visible en el contenido principal del PDF
        

**FLAG OBTENIDA:**  
`picoCTF{puzzl3d_m3tadata_f0und!_ee454950}`

**REFERENCIAS:**

- Herramienta: `exiftool`
    
- Técnica: Análisis de metadatos de PDF
    
- Codificación: Base64
    
- Comando: `exiftool documento.pdf`
    
- Campo clave: Author (contiene la flag codificada)