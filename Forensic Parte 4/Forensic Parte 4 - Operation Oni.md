**RETO:**  
Operation Oni

**DESCRIPCIÓN:**  
Download this disk image, find the key and log into the remote machine.

**SOLUCIÓN:**

1. **Descarga y preparación del entorno**:
    
    - Se descargó la imagen de disco (`disk.img.gz`) desde los servidores de picoCTF en el directorio `/tmp`
        
    - El archivo se descomprimió exitosamente obteniendo una imagen de disco de 241MB
        
2. **Análisis de la estructura del disco**:
    
    - Se utilizó la herramienta `mmls` para identificar las particiones del disco
        
    - Se identificaron dos particiones Linux:
        
        - Partición 1: sectores 2048-206847 (offset 2048)
            
        - Partición 2: sectores 206848-471039 (offset 206848)
            
    - La segunda partición contenía el sistema de archivos principal
        
3. **Exploración del sistema de archivos**:
    
    - Se empleó `fls` para listar el contenido del sistema de archivos en el offset 206848
        
    - Se identificó el directorio `/home` y se exploró recursivamente en busca de archivos SSH
        
    - Se localizó el directorio `.ssh` (inodo 3916) que contenía las claves de autenticación
        
4. **Extracción de la clave privada**:
    
    - Se utilizó `icat` para extraer el contenido del archivo `id_ed25519` (inodo 2345)
        
    - La clave privada OpenSSH se guardó en el archivo `key_file`
        
    - Se ajustaron los permisos del archivo a `600` para cumplir con los requisitos de seguridad de SSH
        
5. **Conexión al servidor remoto**:
    
    - Se estableció conexión SSH usando la clave extraída al puerto 61097
        
    - La autenticación fue exitosa, concediendo acceso al sistema remoto
        
6. **Recuperación de la flag**:
    
    - Una vez en el sistema remoto, se localizó el archivo `flag.txt` en el directorio home del usuario `ctf-player`
        
    - La flag se leyó directamente del archivo
        

**FLAG OBTENIDA:**  
`picoCTF{k3y_5l3u7h_af277f77}`

**NOTAS ADICIONALES:**

- La flag `k3y_5l3u7h_af277f77` se traduce como "key sleuth af277f77" en lenguaje leet
    
- Este reto demostró el uso avanzado del Sleuth Kit para análisis forense de imágenes de disco
    
- La identificación correcta del offset de partición (206848) fue crucial para acceder al sistema de archivos
    
- La exploración recursiva con `fls -r` permitió encontrar directorios ocultos como `.ssh`
    
- La herramienta `icat` fue esencial para extraer archivos específicos de la imagen de disco
    
- El ajuste de permisos de la clave privada es un requisito de seguridad fundamental en SSH
    
- Este tipo de análisis es común en investigaciones forenses donde se necesita recuperar credenciales de sistemas comprometidos
    
- La metodología aplicada (mmls → fls → icat) representa el flujo de trabajo estándar para análisis de medios de almacenamiento
    
- El reto enfatizó la importancia de explorar sistemáticamente todas las particiones y directorios relevantes