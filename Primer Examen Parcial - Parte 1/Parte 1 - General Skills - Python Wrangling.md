**RETO:**  
Python Wrangling

**DESCRIPCIÓN:**  
Python scripts are invoked kind of like programs in the Terminal... Can you run this Python script using this password to get the flag?

**SOLUCIÓN:**

1. **Descarga del script Python**:
    
    - Utilicé `wget` para descargar el script `ende.py` desde la URL proporcionada
        
    - El script implementaba encriptación/desencriptación usando la librería Fernet
        
2. **Búsqueda de archivos adicionales**:
    
    - Descargué `pw.txt` que contenía el password necesario
        
    - Descargué `flag.txt.en` que era el archivo encriptado con la flag
        
3. **Desencriptación de la flag**:
    
    - Ejecuté el script Python con el comando: `python3 ende.py -d flag.txt.en`
        
    - Cuando el script solicitó el password, ingresé el contenido de `pw.txt`
        
    - El script desencriptó y mostró la flag
        

**FLAG OBTENIDA:**  
`picoCTF{4p0110_1n_7h3_h0us3_68f88f93}`

**NOTAS ADICIONALES:**

- El reto demostró el uso práctico de scripts Python para operaciones criptográficas
    
- Se utilizó la librería `cryptography.fernet` para encriptación simétrica
    
- La flag hace referencia a "Apollo in the house"