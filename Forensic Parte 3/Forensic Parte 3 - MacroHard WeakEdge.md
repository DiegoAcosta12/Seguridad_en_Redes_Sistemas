**RETO:**  
MacroHard WeakEdge

**DESCRIPCIÓN:**  
I've hidden a flag in this file. Can you find it? Forensics is fun.pptm

**SOLUCIÓN:**

1. **Análisis inicial del archivo**:
    
    - El archivo `Forensics is fun.pptm` se identificó como Microsoft PowerPoint 2007+ con macros habilitadas
        
    - Los archivos PPTM son contenedores ZIP que almacenan múltiples archivos XML, recursos y macros
        
    - El tamaño del archivo (100,093 bytes) indicaba contenido interno significativo
        
2. **Extracción y exploración del contenido**:
    
    - Se descomprimió el archivo PPTM revelando 87 archivos internos
        
    - La estructura incluía diapositivas, layouts, temas, relaciones y un proyecto VBA
        
    - La búsqueda inicial con `grep -r "picoCTF" .` no encontró resultados visibles
        
3. **Identificación del archivo oculto**:
    
    - Se descubrió un archivo sospechoso llamado `hidden` en el directorio `ppt/slideMasters/`
        
    - El archivo contenía datos codificados: `Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q`
        
    - Los espacios entre caracteres actuaban como ofuscación adicional
        
4. **Decodificación de la flag**:
    
    - Se eliminaron los espacios con `tr -d ' '`
        
    - La cadena resultante se decodificó de Base64 a texto plano
        
    - El proceso reveló la flag auténtica
        

**FLAG OBTENIDA:**  
`picoCTF{D1d_u_kn0w_ppts_r_z1p5}`

**NOTAS ADICIONALES:**

- La flag `D1d_u_kn0w_ppts_r_z1p5` hace referencia directa a la naturaleza de archivos ZIP de las presentaciones PPT
    
- Este reto demostró técnicas forenses esenciales para analizar archivos ofimáticos
    
- Los archivos Office modernos (.pptm, .docx, .xlsx) funcionan como contenedores ZIP comprimidos
    
- La esteganografía en documentos Office puede utilizar archivos con nombres inocentes o carpetas ocultas
    
- El uso de Base64 con espacios adicionales es una técnica común de ofuscación para evitar detección simple
    
- La carpeta `slideMasters` es un lugar frecuente para esconder datos en presentaciones PowerPoint
    
- Este método de ocultamiento sería efectivo contra usuarios que solo abren el archivo normalmente sin examinar su estructura interna