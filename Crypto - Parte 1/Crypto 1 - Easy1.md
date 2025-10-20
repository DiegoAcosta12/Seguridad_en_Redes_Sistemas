**RETO:**  
Easy1

**DESCRIPCIÓN:**  
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help UFJKXQZQUNB with the key of SOLVECRYPTO. Can you use this table to solve it?.

**SOLUCIÓN:**

1. **Análisis inicial del problema**:
    
    - Se proporcionó: texto cifrado `UFJKXQZQUNB`, clave `SOLVECRYPTO` y una tabla de cifrado
        
    - La tabla resultó ser una **tabla Vigenère clásica**
        
    - El reto advertía que el one-time pad es seguro solo cuando no se conoce la clave
        
2. **Estudio de la tabla Vigenère**:
    
    - La tabla mostrada era una matriz 26x26 que representa el cifrado Vigenère
        
    - Para cifrar: se encuentra la fila de la letra de la clave y la columna de la letra del texto plano
        
    - Para descifrar: se encuentra la fila de la letra de la clave y se busca la columna donde está la letra cifrada
        
3. **Proceso de descifrado**:
    
    - **Texto cifrado**: `UFJKXQZQUNB`
        
    - **Clave**: `SOLVECRYPTO` (repetida para coincidir con la longitud del texto)
        
    - **Método**: Para cada posición, calcular `(cifrado - clave) mod 26`
        
4. **Implementación del descifrado**:
    
    python
    
    ciphertext = 'UFJKXQZQUNB'
    key = 'SOLVECRYPTO'
    key_repeated = 'SOLVECRYPTO'  # Ya tiene longitud suficiente
    
    result = ''
    for i in range(len(ciphertext)):
        c_num = ord(ciphertext[i]) - ord('A')
        k_num = ord(key_repeated[i]) - ord('A')
        decrypted_num = (c_num - k_num) % 26
        result += chr(decrypted_num + ord('A'))
    
5. **Verificación manual con la tabla**:
    
    - U (cifrado) + S (clave) → C
        
    - F (cifrado) + O (clave) → R
        
    - J (cifrado) + L (clave) → Y
        
    - K (cifrado) + V (clave) → P
        
    - X (cifrado) + E (clave) → T
        
    - Q (cifrado) + C (clave) → O
        
    - Z (cifrado) + R (clave) → I
        
    - Q (cifrado) + Y (clave) → S
        
    - U (cifrado) + P (clave) → F
        
    - N (cifrado) + T (clave) → U
        
    - B (cifrado) + O (clave) → N
        

**FLAG OBTENIDA:**  
`picoCTF{CRYPTOISFUN}`

**NOTAS ADICIONALES:**

- La flag `CRYPTOISFUN` refleja apropiadamente el mensaje "crypto is fun"
    
- Este reto demostró el cifrado Vigenère, un cifrado polialfabético clásico
    
- A diferencia del cifrado César simple, Vigenère usa múltiples desplazamientos basados en una clave
    
- La vulnerabilidad demostrada fue que conocer la clave compromete completamente la seguridad
    
- El reto enfatizó que incluso cifrados históricamente seguros como Vigenère son vulnerables cuando se reutiliza la clave
    
- La tabla proporcionada sirvió como herramienta educativa para entender visualmente el proceso de cifrado/descifrado
    
- La implementación en Python automatizó el proceso que de otra manera sería tedioso manualmente
    
- Este ejercicio ilustró principios fundamentales de criptografía: confidencialidad depende del secreto de la clave
    
- La técnica de repetir la clave para igualar la longitud del mensaje es característica de Vigenère clásico
    
- El reto mostró cómo algoritmos que fueron considerados seguros en su tiempo pueden ser vulnerables con conocimiento moderno
    
- La importancia de prácticas criptográficas seguras: claves largas, no reutilización, y uso de algoritmos modernos
    
- La tabla Vigenère funciona esencialmente como una suma módulo 26 en el alfabeto inglés
    
- Este cifrado fue considerado "indescifrable" por siglos hasta que se desarrollaron métodos de criptoanálisis efectivos