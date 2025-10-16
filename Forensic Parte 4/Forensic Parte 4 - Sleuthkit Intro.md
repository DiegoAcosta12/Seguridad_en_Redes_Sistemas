**RETO:**  
Sleuthkit Intro

**DESCRIPCIÓN:**  
Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.

**SOLUCIÓN:**

1. **Descarga y preparación de la imagen de disco**:
    
    - Se descargó la imagen comprimida `disk.img.gz` (28.34 MB) en el directorio `/tmp` como se recomendó
        
    - El archivo se descomprimió obteniendo la imagen de disco completa `disk.img`
        
    - Se utilizó el comando `mmls` para analizar la tabla de particiones del disco
        
2. **Análisis de particiones con mmls**:
    
    - El comando `mmls disk.img` reveló la siguiente estructura de particiones:
        
        text
        
        DOS Partition Table
        Offset Sector: 0
        Units are in 512-byte sectors
        
              Slot      Start        End          Length       Description
        000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
        001:  -------   0000000000   0000002047   0000002048   Unallocated
        002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
        
    - Se identificó una única partición Linux (tipo 0x83) en la posición 002
        
    - La partición comienza en el sector 2048 y termina en el sector 204799
        
    - La columna "Length" muestra directamente el tamaño: 202752 sectores
        
3. **Cálculo del tamaño**:
    
    - El tamaño se puede calcular como: End - Start + 1 = 204799 - 2048 + 1 = 202752 sectores
        
    - Alternativamente, la columna "Length" ya proporciona este valor directamente
        
    - Cada sector tiene un tamaño de 512 bytes, pero el reto solo requería el número de sectores
        
4. **Verificación con el servicio remoto**:
    
    - Se estableció conexión con el servicio checker usando: `nc saturn.picoctf.net 63984`
        
    - El servicio solicitó: "What is the size of the Linux partition in the given disk image?"
        
    - Se proporcionó la respuesta: `202752`
        
    - El servicio confirmó la respuesta correcta y proporcionó la flag
        

**FLAG OBTENIDA:**  
`picoCTF{mm15_f7w!}`

**NOTAS ADICIONALES:**

- La flag `mm15_f7w!` parece ser una referencia a "mmls forensics" en formato abreviado/leet
    
- Este reto sirvió como introducción práctica al uso de The Sleuth Kit para análisis forense básico
    
- La herramienta `mmls` es fundamental para examinar tablas de particiones en imágenes de disco
    
- El reto demostró la importancia de entender la estructura de particiones en análisis forense
    
- La partición identificada era del tipo Linux (0x83), que es el código estándar para sistemas de archivos Linux
    
- El espacio no asignado al inicio del disco (sectores 0-2047) típicamente contiene el MBR (Master Boot Record)
    
- La respuesta correcta estaba disponible directamente en la columna "Length" de la salida de mmls
    
- Este ejercicio reforzó el concepto de que las herramientas forenses pueden operar directamente sobre imágenes de disco sin necesidad de montarlas
    
- La conexión al servicio remoto validó el aprendizaje y proporcionó retroalimentación inmediata
    
- El reto enfatizó habilidades esenciales en análisis forense digital: interpretación de tablas de particiones y uso de herramientas especializadas