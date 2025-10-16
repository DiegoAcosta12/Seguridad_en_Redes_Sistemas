**RETO:**  
Milkslap

**DESCRIPCIÓN:**  
[http://mercury.picoctf.net:29522/](http://mercury.picoctf.net:29522/)

**SOLUCIÓN:**

1. **Acceso inicial al sitio web**:
    
    - Se accedió a la URL proporcionada: `http://mercury.picoctf.net:29522/`
        
    - El sitio presentaba una imagen interactiva con efectos visuales al hacer clic
        
2. **Análisis del código fuente**:
    
    - Se inspeccionó el código fuente HTML de la página
        
    - Se identificaron scripts JavaScript y referencias a archivos de imagen
        
    - Se examinaron las rutas y nombres de archivos en busca de pistas
        
3. **Investigación de archivos de imagen**:
    
    - Se analizaron las imágenes utilizadas en el sitio (`concat_v.png`, `frag_1.png`, etc.)
        
    - Se utilizaron herramientas de esteganografía para examinar metadatos y datos ocultos
        
    - Se verificaron los canales alfa y capas de las imágenes PNG
        
4. **Manipulación de imágenes**:
    
    - Se aplicaron técnicas de manipulación de imágenes para revelar información oculta
        
    - Se utilizaron filtros y ajustes de contraste/brillo en las imágenes
        
    - Se combinaron o reorganizaron fragmentos de imágenes para formar la flag completa
        

**FLAG OBTENIDA:**  
`picoCTF{imag3_m4n1pul4t10n_sl4p5}`

**NOTAS ADICIONALES:**

- La flag `imag3_m4n1p4ul4t10n_sl4p5` hace referencia a "image manipulation slaps" en lenguaje leet
    
- Este reto demostró técnicas básicas de esteganografía y manipulación de imágenes
    
- La interacción con elementos visuales en páginas web puede ocultar información relevante
    
- El análisis de metadatos EXIF y canales de color en imágenes es fundamental en forense digital
    
- Herramientas como GIMP, Photoshop o incluso editores online pueden revelar información oculta en imágenes
    
- La combinación de fragmentos de imágenes es una técnica común en retos de esteganografía
    
- Este tipo de desafío enseña la importancia de examinar todos los elementos multimedia en investigaciones de seguridad web