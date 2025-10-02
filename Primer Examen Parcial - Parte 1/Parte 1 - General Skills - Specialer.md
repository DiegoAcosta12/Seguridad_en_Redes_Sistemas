**RETO:**  
Specialer

**DESCRIPCIÓN:**  
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Specialer. Can you get the flag? Connect with `ssh -p 62607 ctf-player@saturn.picoctf.net`.

**SOLUCIÓN:**

1. **Análisis inicial del entorno**:
    
    - Me conecté al servicio via SSH en `saturn.picoctf.net` puerto 62607
        
    - Al acceder al sistema, descubrí que era un **entorno restringido** donde comandos comunes estaban deshabilitados
        
    - Comandos como `ls`, `cat`, `file` no estaban disponibles
        
    - El prompt del sistema era `Specialer$`
        
2. **Identificación de comandos disponibles**:
    
    - Usé el comando `help` para ver qué comandos internos de bash estaban disponibles
        
    - Confirmé que `echo` funcionaba correctamente
        
    - Verifiqué el directorio actual con `pwd`: `/home/ctf-player`
        
3. **Técnicas de enumeración en entorno restringido**:
    
    - Usé `echo *` para listar archivos y directorios en el directorio actual
        
    - Esto reveló tres directorios: `abra`, `ala`, `sim`
        
    - Luego usé `echo */*` para listar el contenido de los subdirectorios:
        
        - `abra/cadabra.txt`, `abra/cadaniel.txt`
            
        - `ala/kazam.txt`, `ala/mode.txt`
            
        - `sim/city.txt`, `sim/salabim.txt`
            
4. **Lectura de archivos sin comandos tradicionales**:
    
    - Utilicé la técnica `echo "$(<archivo)"` para leer el contenido de los archivos
        
    - Empecé leyendo los archivos en `abra/`:
        
        - `abra/cadabra.txt`: "Nothing up my sleeve!"
            
        - `abra/cadaniel.txt`: "Yes, I did it! I'm a true wizard!"
            
    - Continué con los archivos en `ala/`:
        
        - `ala/kazam.txt`: ¡Contenía la flag!
            

**FLAG OBTENIDA:**  
`picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_838b49d1}`

**NOTAS ADICIONALES:**

- La flag `y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3` hace referencia a la técnica poco convencional utilizada para resolver el reto
    
- Este reto demuestra la importancia de conocer alternativas cuando los comandos tradicionales están restringidos
    
- La solución aprovecha características del shell bash que permiten leer archivos usando `$(<archivo)` como substitución de comando
    
- El nombre "Specialer" sugiere que es una versión más restringida del reto "Special" anterior
    

**COMANDOS EJECUTADOS:**

bash

ssh -p 62607 ctf-player@saturn.picoctf.net
pwd
echo *
echo */*
echo "$(<abra/cadabra.txt)"
echo "$(<abra/cadaniel.txt)" 
echo "$(<ala/kazam.txt)"