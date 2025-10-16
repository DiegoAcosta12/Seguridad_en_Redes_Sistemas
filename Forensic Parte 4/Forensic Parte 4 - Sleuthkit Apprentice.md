**RETO:**  
Sleuthkit Apprentice

**DESCRIPCIÓN:**  
Download this disk image and find the flag.

**SOLUCIÓN:**

1. **Descarga y análisis inicial del disco**:
    
    - Se descargó la imagen comprimida `disk.flag.img.gz` (45.33 MB) en el directorio `/tmp` como se recomendó
        
    - El archivo se descomprimió obteniendo una imagen de disco completa
        
    - El análisis con `mmls` reveló tres particiones principales:
        
        - Partición 1: Linux (offset 2048) - sistema de arranque
            
        - Partición 2: Linux Swap
            
        - Partición 3: Linux (offset 360448) - sistema de archivos principal
            
2. **Exploración del sistema de archivos principal**:
    
    - Se utilizó `fls -o 360448` para explorar la partición principal
        
    - Se identificaron los directorios estándar de Linux (`/root`, `/home`, `/etc`, `/boot`, etc.)
        
    - La búsqueda recursiva con `fls -r -o 360448` reveló dos archivos relevantes:
        
        - `flag.txt` (inodo 2082) - archivo con datos numéricos
            
        - `flag.uni.txt` (inodo 2371) - archivo que contenía la flag real
            
3. **Extracción y análisis de los archivos**:
    
    - Se extrajo `flag.txt` usando `icat -o 360448 disk.flag.img 2082`, que contenía datos numéricos: `3.449677 13.056403`
        
    - Se extrajo `flag.uni.txt` usando `icat -o 360448 disk.flag.img 2371`, que contenía la flag en texto claro
        
    - No fue necesario descifrar ningún archivo, ya que la flag estaba disponible directamente
        
4. **Técnicas forenses aplicadas**:
    
    - Identificación y análisis de particiones usando The Sleuth Kit
        
    - Navegación recursiva del sistema de archivos
        
    - Extracción de archivos específicos por número de inodo
        
    - Uso de offsets correctos para acceder a particiones específicas
        

**FLAG OBTENIDA:**  
`picoCTF{by73_5urf3r_3497ae6b}`

**NOTAS ADICIONALES:**

- La flag `by73_5urf3r_3497ae6b` parece traducirse como "byte surfer" en lenguaje leet, apropiado para un reto de análisis forense
    
- Los datos numéricos en `flag.txt` (`3.449677, 13.056403`) podrían ser coordenadas que apuntan a una ubicación en Camerún, África
    
- Este reto demostró la importancia de explorar múltiples archivos con nombres similares durante investigaciones forenses
    
- La flag estaba accesible sin necesidad de descifrado, a diferencia de otros retos más complejos de la misma categoría
    
- El uso de offsets correctos fue crucial para acceder a la partición que contenía los archivos relevantes
    
- La técnica de buscar archivos por nombre con `grep -i "flag"` fue efectiva para identificar objetivos potenciales
    
- Este reto sirvió como introducción práctica al uso de The Sleuth Kit para análisis forense de imágenes de disco
    
- La importancia de verificar tanto archivos visibles como potenciales archivos eliminados o ocultos en investigaciones forenses
    
- El reto enfatizó habilidades básicas pero esenciales en análisis forense digital: identificación de particiones, navegación de sistemas de archivos y recuperación de archivos específicos