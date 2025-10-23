**RETO:** Ph4nt0m 1ntrud3r

**DESCRIPCION:** A digital ghost has breached my defenses, and my sensitive data has been stolen! Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag by analyzing the provided PCAP file.

**SOLUCION:**

- Descargué el archivo PCAP usando wget
    
- Usé **`tshark`** para analizar el tráfico de red
    
- Identifiqué que el atacante usó paquetes TCP SYN con datos ocultos
    
- Apliqué filtros para paquetes con longitudes específicas: `tcp.len==12 || tcp.len==4`
    
- Ordené los paquetes por tiempo usando `frame.time_relative` y `sort -n`
    
- Extraje los datos del segmento TCP y los convertí de hexadecimal con `xxd -r -p`
    
- Decodifiqué los datos Base64 para obtener la flag
    

Comando final:

bash

tshark -r myNetworkTraffic.pcap -Y "tcp.len==12 || tcp.len==4" -T fields -e frame.time_relative -e tcp.segment_data | sort -n | awk '{print $2}' | xxd -r -p | base64 -d

**Flag:** `picoCTF{1t_w4snt_th4t_34sy_tbh_4r_2e1ff063}`

**NOTAS ADICIONALES:**

- El atacante utilizó exfiltración de datos oculta en paquetes TCP SYN
    
- Los datos estaban codificados en Base64 dentro del payload TCP
    
- El filtro por longitud de paquete fue esencial para separar la señal del ruido
    

**REFERENCIAS:**

- [https://www.wireshark.org/docs/man-pages/tshark.html](https://www.wireshark.org/docs/man-pages/tshark.html)
    
- [https://linux.die.net/man/1/base64](https://linux.die.net/man/1/base64)