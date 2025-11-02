**RETO:** substitution1

**DESCRIPCION:**  
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.

**SOLUCION:**

- Descargué el archivo message.txt que contenía un cifrado por sustitución sin clave explícita
    
- Usé ataque de frecuencia para analizar las letras más comunes
    
- Identifiqué patrones de palabras comunes en inglés (THE, AND, etc.)
    
- Ajusté manualmente el mapeo basado en la estructura del texto y puntuación
    
- El texto descifrado reveló la flag al final
    

**Técnicas utilizadas:**

- Análisis de frecuencia de letras (E, T, A, O, I, N son las más comunes en inglés)
    
- Identificación de palabras cortas comunes (THE, AND, IS, etc.)
    
- Uso de puntuación y estructura de oraciones para verificar suposiciones
    

**Mapeo final utilizado:**

text

S→A, Y→N, T→D, E→E, A→H, K→O, D→T, J→I, B→F, R→R, N→M, Z→U, 
O→C, H→S, C→L, M→P, G→W, X→B, W→Y, V→V, L→K, Q→G, U→X, P→Z

**Flag:** `picoCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}`

**NOTAS:**

- Cifrado por sustitución monoalfabético sin clave proporcionada
    
- Requirió análisis criptográfico manual usando frecuencia y patrones lingüísticos
    
- La flag hace referencia a "FREQUENCY ATTACKS ARE COOL"
    
- Demuestra la vulnerabilidad de los cifrados por sustitución simples ante análisis de frecuencia