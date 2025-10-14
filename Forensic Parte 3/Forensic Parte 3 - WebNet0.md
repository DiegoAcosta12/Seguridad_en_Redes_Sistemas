**RETO:**  
WebNet0

**DESCRIPCIÓN:**  
We found this packet capture and key. Recover the flag.

**SOLUCIÓN:**

1. **Descarga y preparación de los archivos**:
    
    - Se descargaron el archivo de captura de red (`capture.pcap`) y la clave privada (`picopico.key`)
        
    - Los archivos se obtuvieron de los servidores oficiales de picoCTF
        
2. **Configuración de Wireshark para descifrado SSL/TLS**:
    
    - Se abrió el archivo `capture.pcap` en Wireshark
        
    - En las preferencias de TLS (`Edit → Preferences → Protocols → TLS`), se configuró la lista de claves RSA
        
    - Se agregó `picopico.key` como archivo de clave para descifrar el tráfico en el puerto 443
        
3. **Análisis del tráfico descifrado**:
    
    - Se aplicaron filtros para visualizar el tráfico HTTP/2: `http2`
        
    - Se utilizó la función "Follow TLS Stream" para examinar las comunicaciones descifradas
        
    - Se identificaron múltiples streams de datos que contenían comunicación cliente-servidor
        
4. **Extracción de la flag**:
    
    - En uno de los streams TLS descifrados, se encontró la flag en texto claro
        
    - La flag estaba embedida dentro del tráfico HTTP/2 previamente cifrado
        
    - La clave privada permitió descifrar las comunicaciones SSL/TLS capturadas
        

**FLAG OBTENIDA:**  
`picoCTF{nongshim.shrimp.crackers}`

**NOTAS ADICIONALES:**

- La flag hace referencia a "galletas de camarón Nongshim", un producto alimenticio coreano
    
- Este reto demostró la importancia de las claves privadas en el análisis forense de redes
    
- El descifrado de tráfico SSL/TLS con Wireshark es una técnica estándar en investigaciones de seguridad
    
- La captura contenía tráfico HTTP/2, protocolo común en aplicaciones web modernas
    
- La posesión de la clave privada permite descifrar comunicaciones previamente grabadas, highlighting la criticalidad de proteger las claves criptográficas
    
- Este tipo de análisis es fundamental en investigaciones de incidentes de seguridad y auditorías de red