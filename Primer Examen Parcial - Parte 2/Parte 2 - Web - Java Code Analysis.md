**RETO:**  
Java Code Analysis

**DESCRIPCIÓN:**  
BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!  
Credentials: Username: "user", Password: "user"  
Website: [http://saturn.picoctf.net:54879/](http://saturn.picoctf.net:54879/)

**SOLUCIÓN:**

1. **Análisis inicial de la aplicación**:
    
    - Accedí al sitio web BookShelf Pico con las credenciales proporcionadas: `user`/`user`
        
    - La aplicación utilizaba autenticación basada en tokens JWT (JSON Web Tokens)
        
    - Identifiqué que el token JWT contenía información del rol del usuario
        
2. **Obtención y análisis del token JWT**:
    
    - Después del login exitoso, la aplicación proporcionó un token JWT:
        
        text
        
        eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiRnJlZSIsImlzcyI6ImJvb2tzaGVsZiIsImV4cCI6MTc2MDA2NTU0NywiaWF0IjoxNzU5NDYwNzQ3LCJ1c2VySWQiOjEsImVtYWlsIjoidXNlciJ9.kyr4lexZ2g4QTr_Cg6COqxEEkF5o3qkghxxDZ2zXhCM
        
    - Decodifiqué el token y analicé su estructura:
        
        - Header: `{"typ":"JWT","alg":"HS256"}`
            
        - Payload: `{"role":"Free","iss":"bookshelf","exp":1760065547,"iat":1759460747,"userId":1,"email":"user"}`
            
3. **Identificación de la vulnerabilidad**:
    
    - La aplicación confiaba en el claim `role` del token JWT para determinar los privilegios del usuario
        
    - El algoritmo de firma era HS256, lo que sugiere un secreto compartido
        
    - Sospeché que el secreto de firma podría ser débil o predecible
        
4. **Ataque de JWT tampering**:
    
    - Modifiqué el payload del token cambiando el rol de `"Free"` a `"Admin"`
        
    - Utilicé el secreto débil `"1234"` para re-firmar el token
        
    - Generé un nuevo token JWT válido:
        
        text
        
        eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NjAwNjQ0ODUsImlhdCI6MTc1OTQ1OTY4NSwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.7p6H4gR4vJxWlL8kY9qQ2mTdN1vXzBwKcA3jE5sGhFo
        
5. **Explotación y obtención de la flag**:
    
    - Utilicé el token modificado para acceder a la aplicación como administrador
        
    - Accedí al libro "Flag" que estaba restringido para usuarios normales
        
    - La flag fue revelada exitosamente
        

**FLAG OBTENIDA:**  
`picoCTF{w34k_jwt_n0t_g00d_6e5d7df5}`

**NOTAS ADICIONALES:**

- La flag `w34k_jwt_n0t_g00d` describe perfectamente la vulnerabilidad explotada
    
- Este reto demuestra los peligros de usar secretos débiles en la firma de tokens JWT
    
- La aplicación confiaba ciegamente en los claims del token sin validación adicional en el servidor
    
- El secreto `"1234"` es extremadamente débil y fácil de adivinar
    
- Este tipo de ataque es posible cuando los desarrolladores subestiman la importancia de secretos fuertes
    
- La vulnerabilidad permitió escalar privilegios de usuario normal a administrador