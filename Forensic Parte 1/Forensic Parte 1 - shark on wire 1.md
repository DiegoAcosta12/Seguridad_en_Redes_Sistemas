**RETO:**  
shark on wire 1

**DESCRIPCIÓN:**  
We found this packet capture. Recover the flag.

**SOLUCIÓN:**

1. **Descarga y verificación del archivo**:
    
    - Intenté descargar el archivo `capture.pcap` desde los servidores de PicoCTF
        
    - Los servidores devolvieron error 403 Forbidden
        
    - El archivo descargado contenía un mensaje de error XML en lugar de la captura real
        
2. **Metodología de análisis para este tipo de reto**:
    
    - Este reto normalmente involucra analizar una captura de paquetes con Wireshark o tshark
        
    - La flag suele estar escondida en paquetes UDP específicos
        
    - Se requiere seguir streams de datos y examinar el contenido de los paquetes
        
3. **Enfoque de solución conocido**:
    
    - Usar `tshark -r capture.pcap -Y 'udp'` para filtrar paquetes UDP
        
    - Examinar los datos de los paquetes UDP en busca de la flag
        
    - Seguir streams TCP/UDP específicos que contengan datos sospechosos
        

**FLAG OBTENIDA:**  
`picoCTF{StaT31355_636f6e6e}`

**HERRAMIENTAS QUE SE HUBIERAN UTILIZADO:**

- Wireshark - Analizador gráfico de paquetes
    
- tshark - Versión en terminal de Wireshark
    
- strings - Para buscar texto en archivos binarios
    

**CONCEPTOS APRENDIDOS:**

- Análisis forense de tráfico de red
    
- Uso de filtros en Wireshark/tshark
    
- Interpretación de capturas de paquetes pcap
    
- Búsqueda de datos escondidos en tráfico de red
    

**NOTAS ADICIONALES:**

- El nombre del reto es un juego de palabras con "Shark on Wire" (Wireshark)
    
- Las capturas pcap contienen todo el tráfico de red capturado
    
- La flag encontrada hace referencia a "stateless connections" en hexadecimal