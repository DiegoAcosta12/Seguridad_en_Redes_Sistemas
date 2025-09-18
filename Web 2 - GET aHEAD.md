**RETO:**  
GET aHEAD

**DESCRIPCIÓN:**  
Find the flag being held on this server to get ahead of the competition  
[http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)  
Maybe you have more than 2 choices. Check out tools like Burpsuite to modify your requests and look at the responses.

**SOLUCIÓN:**

1. Accedí al sitio web y observé que contenía botones que cambiaban el color de fondo, lo que sugería el uso de métodos HTTP (GET y POST).
    
2. Usé la herramienta **curl** para realizar una solicitud HEAD al servidor (ya que el reto insinúa el uso de métodos alternativos):
    
    bash
    
    Copy
    
    Download
    
    curl -I http://mercury.picoctf.net:53554/
    
3. La respuesta mostró la flag en el encabezado HTTP:  
    `flag: picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}`
    
4. Alternativamente, usé **Burp Suite** para interceptar una solicitud GET, cambié el método a HEAD y confirmé que la flag aparecía en los encabezados de respuesta.
    

**FLAG OBTENIDA:**  
`picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}`

**NOTAS ADICIONALES:**

- El método HEAD en HTTP solicita solo los encabezados de respuesta (sin cuerpo), lo que a veces revela información oculta.
	    
- Este reto enseña la importancia de probar diferentes métodos HTTP (GET, POST, HEAD, etc.) en auditorías web.
    

**REFERENCIAS:**

- [HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
    
- [Using curl](https://curl.se/docs/)