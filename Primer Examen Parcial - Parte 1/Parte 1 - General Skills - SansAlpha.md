**RETO:**  
SansAlpha

**DESCRIPCIÓN:**  
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.  
`ssh -p 61744 ctf-player@mimas.picoctf.net`  
Password: `6dd28e9b`

**SOLUCIÓN:**

1. **Conexión al entorno restringido**:
    
    - Me conecté al servidor SSH que tenía un entorno con teclado restringido
        
    - Solo se permitían números y símbolos, no caracteres alfabéticos
        
    - El script `sansalpha.py` filtraba cualquier entrada que contuviera letras
        
2. **Exploración del sistema**:
    
    - Usé comodines (`*`, `?`) para enumerar archivos y directorios
        
    - Identifiqué un directorio `blargh` que contenía el archivo `flag.txt`
        
    - Los comandos tradicionales como `cat`, `ls`, etc. no estaban disponibles directamente
        
3. **Bypass de las restricciones**:
    
    - Utilicé patrones con comodines para ejecutar comandos sin usar letras
        
    - El comando exitoso fue: `/*/???[!_]64 */????.*`
        
    - Este comando se expandió a `/usr/bin/base64 /home/ctf-player/blargh/flag.txt`
        
4. **Obtención de la flag**:
    
    - El comando ejecutó `base64` en el archivo flag, produciendo salida codificada
        
    - Decodifiqué el resultado Base64 para obtener la flag
        

**FLAG OBTENIDA:**  
`picoCTF{7h15_mu171v3r53_15_m4dn355_145256ec}`

**NOTAS ADICIONALES:**

- La flag `7h15_mu171v3r53_15_m4dn355` (this multiverse is madness) refleja perfectamente la naturaleza del reto
    
- El uso de comodines y patrones fue esencial para bypass las restricciones del teclado
    
- El comando `???[!_]64` usó una clase de caracteres negada para encontrar `base64` específicamente
    
- Este reto demostró técnicas avanzadas de expansión de shell en entornos restringidos