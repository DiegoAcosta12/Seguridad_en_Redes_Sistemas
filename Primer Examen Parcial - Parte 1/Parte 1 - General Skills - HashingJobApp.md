**RETO:**  
HashingJobApp

**DESCRIPCIÓN:**  
If you want to hash with the best, beat this test!  
nc [saturn.picoctf.net](https://saturn.picoctf.net/) 55019

**SOLUCIÓN:**

1. **Conexión al servidor**:
    
    - Utilicé el comando `nc saturn.picoctf.net 55019` para conectarme al desafío interactivo
        
2. **Resolución del desafío de hashing**:
    
    - El servidor presentó una serie de textos para calcular sus hashes MD5
        
    - Para cada texto, calculé el hash MD5 usando: `echo -n "texto" | md5sum`
        
    - Los textos incluían: "Chinatown", "Michelangelo", "Casablanca", "commuting", "Adam Sandler"
        
3. **Obtención de la flag**:
    
    - Después de responder correctamente todas las preguntas de hashing, el servidor entregó la flag
        
    - La flag fue: `picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}`
        

**FLAG OBTENIDA:**  
`picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}`

**NOTAS ADICIONALES:**

- El reto demostró el uso práctico de funciones hash MD5
    
- Se requirió calcular hashes de múltiples strings de manera consecutiva
    
- La flag hace referencia a "application received"