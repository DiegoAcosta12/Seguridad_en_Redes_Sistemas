**RETO:**  
WebNet1

**DESCRIPCIÓN:**  
We found this packet capture and key. Recover the flag.

**SOLUCIÓN:**

1. **Descarga y preparación de los archivos**:
    
    - Se descargaron el archivo de captura de red (`capture.pcap`) y la clave privada (`picopico.key`) desde los servidores de picoCTF
        
    - Los archivos se verificaron para asegurar su integridad antes del análisis
        
2. **Configuración de Wireshark para descifrado SSL/TLS**:
    
    - Se abrió el archivo `capture.pcap` en Wireshark
        
    - En las preferencias de TLS (`Edit → Preferences → Protocols → TLS`), se configuró la lista de claves RSA
        
    - Se agregó `picopico.key` como archivo de clave para descifrar el tráfico SSL/TLS
        
    - Se especificó el puerto 443 para aplicar el descifrado al tráfico HTTPS
        
3. **Análisis del tráfico descifrado**:
    
    - Se aplicaron filtros para visualizar el tráfico HTTP/2: `http2`
        
    - Se utilizó la función "Follow TLS Stream" para examinar las comunicaciones descifradas en texto plano
        
    - Se identificaron múltiples streams de datos que contenían comunicación cliente-servidor cifrada
        
4. **Extracción de la flag**:
    
    - En uno de los streams TLS descifrados, se encontró la flag en texto claro entre el tráfico HTTP/2
        
    - La flag estaba oculta dentro de las comunicaciones previamente cifradas entre cliente y servidor
        
    - La clave privada proporcionada permitió revertir el cifrado aplicado durante la captura
        

**FLAG OBTENIDA:**  
`picoCTF{honey.roasted.peanuts}`

**NOTAS ADICIONALES:**

- La flag hace referencia a "maní tostado con miel", continuando con la temática de alimentos
    
- Este reto reforzó los conceptos de análisis de tráfico cifrado aprendidos en WebNet0
    
- La capacidad de descifrar tráfico SSL/TLS con una clave privada es fundamental en investigaciones forenses
    
- Wireshark demostró ser la herramienta estándar para análisis avanzado de archivos pcap
    
- La técnica de "Follow TLS Stream" es esencial para visualizar conversaciones completas entre cliente y servidor
    
- La protección de claves privadas es crítica para la seguridad de las comunicaciones cifradas
    
- Este tipo de ejercicio prepara para escenarios reales de análisis de tráfico malicioso o investigaciones de incidentes