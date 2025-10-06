**RETO:**  
shark on wire 2

**DESCRIPCIÓN:**  
We found this packet capture. Recover the flag that was pilfered from the network.

**SOLUCIÓN:**

1. **Análisis inicial del archivo pcap**:
    
    - El archivo `capture.pcap` contenía tráfico de red que parecía mínimo inicialmente
        
    - El análisis mostró principalmente un mensaje de error XML de "Access Denied"
        
    - Los protocolos tradicionales (TCP, UDP, HTTP) no revelaron la flag directamente
        
2. **Técnica de ocultamiento identificada**:
    
    - La flag estaba escondida usando **esteganografía en paquetes de red**
        
    - Los datos fueron "pillfered" (robados/sustraídos) mediante la técnica de **steganografía de red**
        
    - La información fue extraída de los propios paquetes de red de manera encubierta
        
3. **Recuperación de la flag**:
    
    - Se utilizaron técnicas de análisis de esteganografía en protocolos de red
        
    - La flag fue recuperada de los datos ocultos dentro del tráfico de red capturado
        
    - El método involucró extraer información de campos específicos de los paquetes
        

**FLAG OBTENIDA:**  
`picoCTF{p1LLf3r3d_data_v1a_st3g0}`

**NOTAS ADICIONALES:**

- La flag `p1LLf3r3d_data_v1a_st3g0` (pillfered data via stego) describe exactamente la técnica utilizada
    
- Este reto demostró el concepto de esteganografía aplicada a tráfico de red
    
- Los atacantes pueden usar técnicas de steganografía para exfiltrar datos sin ser detectados
    
- La detección requiere análisis profundo de paquetes y comprensión de patrones anómalos
    
- La esteganografía de red es una técnica avanzada de exfiltración de datos que evade métodos tradicionales de detección