**RETO:**  
findme

**DESCRIPCIÓN:**  
Help us test the form by submitting the username as test and password as test! The website running here.  
[http://saturn.picoctf.net:59692/](http://saturn.picoctf.net:59692/)

**SOLUCIÓN:**

1. **Análisis inicial del sitio web**:
    
    - Accedí al sitio web que presentaba un formulario de login simple
        
    - El formulario enviaba credenciales a `/login` mediante método POST
        
    - Las pruebas con curl mostraron que siempre se obtenía la misma respuesta: "try username:test and password:test!"
        
    - No se encontraron archivos o directorios visibles mediante enumeración tradicional
        
2. **Uso de Burp Suite para análisis de tráfico**:
    
    - Configuré Burp Suite como proxy para interceptar el tráfico HTTP
        
    - Navegué por la aplicación web mientras Burp Suite capturaba todas las peticiones
        
    - Identifiqué que la aplicación redirigía entre diferentes páginas después del login
        
3. **Descubrimiento de las partes de la flag**:
    
    - Analicé los headers HTTP en las peticiones interceptadas
        
    - Encontré partes de la flag codificadas en Base64 en el header `Referer`:
        
        - Primera parte: `cGljb0NURntwcm94aWVzX2Fs`
            
        - Segunda parte: `bF90aGVfd2F5XzI1YmJhZTlhfQ==`
            
4. **Decodificación y reconstrucción de la flag**:
    
    - Decodifiqué las partes Base64:
        
        bash
        
        echo "cGljb0NURntwcm94aWVzX2Fs" | base64 -d

        
        echo "bF90aGVfd2F5XzI1YmJhZTlhfQ==" | base64 -d  
    
        
    - Uní las partes para formar la flag completa
        

**FLAG OBTENIDA:**  
`picoCTF{proxies_all_the_way_25bbae9a}`

**NOTAS ADICIONALES:**

- La flag `proxies_all_the_way` hace referencia al uso de Burp Suite como proxy para interceptar el tráfico
    
- Este reto demuestra la importancia de analizar todo el tráfico HTTP, no solo las respuestas visibles
    
- Las flags o información sensible pueden estar ocultas en headers HTTP como `Referer`, `Location`, o cookies
    
- Burp Suite es una herramienta esencial para pruebas de seguridad web que permite analizar tráfico de forma detallada
    
- El enfoque tradicional de enumeración con curl no fue efectivo porque la flag estaba en el flujo de navegación normal
    
- El reto enfatiza que "findme" significa encontrar información en lugares no obvios del protocolo HTTP