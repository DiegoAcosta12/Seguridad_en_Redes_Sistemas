**RETO:**  
Operation Orchid

**DESCRIPCIÓN:**  
Download this disk image and find the flag.

**SOLUCIÓN:**

1. **Descarga y análisis inicial del disco**:
    
    - Se descargó la imagen comprimida `disk.flag.img.gz` (42.31 MB) en el directorio `/tmp`
        
    - El archivo se descomprimió obteniendo una imagen de disco de aproximadamente 42MB
        
    - El análisis con `mmls` reveló tres particiones principales:
        
        - Partición 1: Linux (offset 2048) - sistema de arranque
            
        - Partición 2: Linux Swap
            
        - Partición 3: Linux (offset 411648) - sistema de archivos principal
            
2. **Exploración del sistema de archivos principal**:
    
    - Se utilizó `fls` con offset 411648 para explorar la partición principal
        
    - Se identificaron los directorios estándar de Linux (`/root`, `/home`, `/etc`, etc.)
        
    - La búsqueda recursiva con `fls -r` reveló dos archivos relevantes en `/root`:
        
        - `flag.txt` (inodo 1876)
            
        - `flag.txt.enc` (inodo 1782)
            
3. **Extracción y análisis de los archivos**:
    
    - Se extrajo `flag.txt` que contenía coordenadas geográficas: `-0.881573 34.311733`
        
    - Se extrajo `flag.txt.enc` identificado como datos cifrados con OpenSSL con salted password
        
    - Los intentos iniciales de descifrado usando las coordenadas como contraseña fallaron
        
4. **Búsqueda de pistas adicionales**:
    
    - Se examinó el historial de comandos (`.ash_history`, inodo 1875) del usuario root
        
    - El historial reveló el comando exacto usado para cifrar el archivo:
        
        bash
        
        openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
        
    - También mostró que el archivo original fue eliminado con `shred -u flag.txt` después del cifrado
        
5. **Descifrado exitoso**:
    
    - Se utilizó la contraseña `unbreakablepassword1234567` encontrada en el historial
        
    - A pesar de una advertencia sobre el método de derivación de clave, el descifrado fue exitoso
        
    - El archivo descifrado contenía la flag en texto claro
        

**FLAG OBTENIDA:**  
`picoCTF{h4un71ng_p457_0a710765}`

**NOTAS ADICIONALES:**

- La flag `h4un71ng_p457_0a710765` se traduce como "haunting past 0a710765" en lenguaje leet
    
- Las coordenadas encontradas en `flag.txt` (`-0.881573, 34.311733`) corresponden a una ubicación en Tanzania, África
    
- Este reto demostró la importancia de examinar el historial de comandos en investigaciones forenses
    
- La contraseña `unbreakablepassword1234567` resultó ser irónicamente "rompible" gracias al historial accesible
    
- El uso de `shred -u` para eliminar el archivo original no fue efectivo ya que los datos aún eran recuperables de la imagen de disco
    
- La técnica de cifrado utilizada (AES-256 con salt) es criptográficamente segura, pero la exposición de la contraseña en el historial comprometió la seguridad
    
- Este escenario es común en investigaciones de seguridad donde atacantes o usuarios descuidados dejan rastros en el historial del sistema
    
- El reto enfatizó la necesidad de prácticas seguras de manejo de contraseñas y la importancia de limpiar historiales sensibles