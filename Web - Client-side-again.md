**RETO:**  
Client-side-again

**DESCRIPCIÓN:**  
Can you break into this super secure portal?  
[https://jupiter.challenges.picoctf.org/problem/6353/](https://jupiter.challenges.picoctf.org/problem/6353/) (link) or [http://jupiter.challenges.picoctf.org:6353](http://jupiter.challenges.picoctf.org:6353/)

**SOLUCIÓN:**

1. Accedí al sitio web [http://jupiter.challenges.picoctf.org:6353](http://jupiter.challenges.picoctf.org:6353/).
    
2. Inspeccioné el código fuente y encontré un script JavaScript ofuscado que validaba la contraseña en el cliente.
    
3. Desofusqué el código manualmente y con la ayuda de herramientas en línea para entender la lógica:
    
    - El array `_0x5a46` contenía strings clave: `['0a029}', '_again_5', 'this', 'Password Verified', 'Incorrect password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this']`.
        
    - La función `verify()` comparaba segmentos de la contraseña con estos valores.
        
4. Reconstruí la contraseña analizando las condiciones:
    
    - `0-8`: 'picoCTF{'
        
    - `8-16`: 'not_this'
        
    - `16-24`: '_again_5'
        
    - `24-32`: '0a029}'
        
5. La contraseña completa es: `picoCTF{not_this_again_50a029}`.
    
6. Ingresé esta contraseña en el campo de contraseña y hice clic en "verify", lo que resultó en un mensaje de "Password Verified".
    

**FLAG OBTENIDA:**  
`picoCTF{not_this_again_50a029}`

**NOTAS ADICIONALES:**

- El reto demostró los riesgos de la validación de contraseñas en el lado del cliente, especialmente cuando el código está ofuscado pero aún es reversible.
    
- La desofuscación reveló que la flag era la contraseña misma.
    

**REFERENCIAS:**

- [Obfuscated JavaScript](https://en.wikipedia.org/wiki/Obfuscation_\(software\))