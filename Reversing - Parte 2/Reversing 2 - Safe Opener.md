**RETO:** Safe Opener

**DESCRIPCION:**  
Can you open this safe? I forgot the key to my safe but this program is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

**SOLUCION:**

- Descargué el archivo SafeOpener.java que contenía el código fuente del programa
    
- Analicé el código y encontré que la función `openSafe` comparaba el password con un string hardcodeado en Base64
    
- El string codificado era: `"cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz"`
    
- Identifiqué que el programa codificaba la entrada del usuario en Base64 y la comparaba con este string
    
- Decodifiqué el string Base64 usando el comando `base64 -d` para obtener el password original
    

**Proceso de solución:**

1. **Descargar el archivo:**
    
    bash
    
    wget https://artifacts.picoctf.net/c/83/SafeOpener.java
    
2. **Analizar el código:**
    
    bash
    
    cat SafeOpener.java
    
3. **Identificar el string Base64 hardcodeado:**
    
    - Encontrado en la función `openSafe`: `"cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz"`
        
4. **Decodificar Base64:**
    
    bash
    
    echo "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz" | base64 -d
    
5. **Resultado:** `pl3as3_l3t_m3_1nt0_th3_saf3`
    

**Flag:** `picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}`

**NOTAS:**

- El reto demostró los peligros de almacenar passwords en código fuente de forma hardcodeada
    
- Aunque el password estaba codificado en Base64, esta no es una forma segura de proteger información sensible
    
- Base64 es una codificación, no un cifrado, por lo que es fácilmente reversible
    
- La password "pl3as3_l3t_m3_1nt0_th3_saf3" significa "please let me into the safe" en leet speak
    
- Nunca se deben almacenar credenciales o información sensible en código fuente, incluso si están codificadas
    
- Los strings hardcodeados pueden ser fácilmente extraídos mediante análisis estático del código