### **RETO:** Hidden in plainsight

**DESCRIPCIÓN:**  
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag.

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - La imagen `img.jpg` parece un archivo JPG normal visualmente
        
    - Se revisaron los metadatos EXIF como sugería el tip
        
    - El tamaño del archivo es de 183KB
        
2. **Proceso de resolución**:
    
    - Se utilizó el comando `exiftool` para examinar los metadatos
        
    - Se identificó un campo de comentario sospechoso en los metadatos
        
    - El comentario contenía datos codificados en Base64
        
    - Se decodificó el Base64 revelando información sobre steghide
        
    - Se decodificó la contraseña en Base64
        
    - Se usó steghide con la contraseña para extraer el archivo oculto
        
3. **Descubrimiento clave**:
    
    - En el campo `Comment` de los metadatos EXIF se encontró: `c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9`
        
    - Al decodificar: `steghide:cEF6endvcmQ=`
        
    - La contraseña decodificada: `pAzzword`
        
    - Steghide extrajo el archivo `flag.txt`
        

**FLAG OBTENIDA:**  
`picoCTF{h1dd3n_1n_1m4g3_1c55ccd0}`

**REFERENCIAS:**

- Herramienta: `exiftool`
    
- Herramienta: `steghide`
    
- Técnica: Esteganografía en metadatos EXIF
    
- Comando: `exiftool img.jpg`
    
- Comando: `echo "c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9" | base64 -d`
    
- Comando: `echo "cEF6endvcmQ=" | base64 -d`
    
- Comando: `steghide extract -sf img.jpg -p "pAzzword"`