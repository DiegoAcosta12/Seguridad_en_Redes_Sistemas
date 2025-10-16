### **RETO:** byp4ss3d

**DESCRIPCIÓN:**  
A university's online registration portal asks students to upload their ID cards for verification. The developer put some filters in place to ensure only image files are uploaded but are they enough? Take a look at how the upload is implemented. Maybe there's a way to slip past the checks and interact with the server in ways you shouldn't.

**SOLUCIÓN:**

1. **Análisis inicial**:
    
    - Portal de subida de archivos en: [http://amiable-citadel.picoctf.net:61503](http://amiable-citadel.picoctf.net:61503/)
        
    - Filtros para solo permitir imágenes (JPG, PNG, GIF)
        
    - Sistema Apache con PHP
        
2. **Proceso de resolución**:
    
    - Se identificó que se podía subir archivos .htaccess
        
    - Se subió un archivo .htaccess configurando Apache para ejecutar archivos .test como PHP
        
    - Se subió un archivo shell.test con código PHP para ejecución de comandos
        
    - Se usó el shell web para explorar el sistema de archivos
        
    - Se encontró y leyó el archivo flag.txt
        
3. **Descubrimiento clave**:
    
    - El archivo .htaccess permitió bypass de restricciones de extensión
        
    - Configuración: `AddType application/x-httpd-php .test`
        
    - La flag estaba en `/var/www/flag.txt`
        
    - Comando ejecutado: `cat /var/www/flag.txt`
        

**FLAG OBTENIDA:**  
`picoCTF{s3rv3r_byp4ss_9e7008ba}`

**REFERENCIAS:**

- URL: [http://amiable-citadel.picoctf.net:61503](http://amiable-citadel.picoctf.net:61503/)
    
- Técnica: Bypass de filtros de subida via .htaccess
    
- Herramientas: `curl`, Apache .htaccess
    
- Comandos:
    
    - Subida de .htaccess con configuración PHP
        
    - Subida de shell.test con código PHP
        
    - Ejecución remota de comandos via parámetro cmd